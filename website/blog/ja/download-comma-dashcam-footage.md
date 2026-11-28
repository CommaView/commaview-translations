---
title: "comma デバイスからドライブレコーダー映像をダウンロードする方法"
description: "comma の映像ファイル、comma 3 / 3X / four の違い、そしてルートの映像をいちばん安全に書き出す方法を解説する実践ガイド。"
date: 2026-05-14
updatedDate: 2026-10-22
slug: download-comma-dashcam-footage
tags:
  - comma device video
  - dashcam footage
  - openpilot tools
  - SSH
heroLabel: "comma デバイスガイド"
draft: false
---

comma デバイスから映像を取り出したいですか？ よく使われる方法は、comma connect、Openpilot Toolkit、または SSH/SFTP による直接アクセスです。

つまずきやすいのはファイルの構成です。comma デバイスは openpilot のルートを、1 本の長いドライブレコーダー映像ではなく、短いセグメントに分けて記録します。各セグメントには、生のカメラファイル、プレビュー映像、ルートのログが含まれることがあります。これがわかれば、映像の書き出しはぐっとわかりやすくなります。

最初に大事な注意を 1 つ。comma デバイスは道路の映像、デバッグ、ルートの確認に役立ちますが、専用のドライブレコーダーの代わりにそのまま使えるものではありません。

## comma デバイスは便利なカメラだが、完璧なドライブレコーダーではない

専用のドライブレコーダーは、証拠を残すことを中心に作られています。すばやい起動、事故に強い作り、駐車監視モード、簡単なファイルの書き出し、リアカメラの選択肢、取り外せるストレージです。

comma デバイスは openpilot を動かすために作られています。ルートのデータを記録するのは、それが運転モデル、デバッグ、connect のプレビュー、開発に役立つからです。その映像には価値がありますが、トレードオフもあります。

- SD カードを抜くより映像を取り出しにくいことがある
- 事故や突然の電源断で、直前の映像が失われることがある
- 駐車中の録画は主な設計目標ではない
- 後方のドライブレコーダー映像は含まれない
- デバイスに空き容量が必要になると、古いローカルデータは削除される

確実な事故映像が目的なら、本物のドライブレコーダーを使ってください。openpilot のルート映像、開発のための確認、ローカルでの映像書き出しが目的なら、comma での手順は覚えておく価値があります。

## openpilot はどんなファイルを記録するのか

openpilot の公式なログのドキュメントでは、ルートは 1 分ごとのセグメントとして説明されています。現在の openpilot は、セグメントごとに次の種類のファイルを記録します。

| ファイル | 内容 |
| --- | --- |
| `fcamera.hevc` | 道路カメラの映像、H.265/HEVC |
| `ecamera.hevc` | 広角の道路カメラの映像、H.265/HEVC |
| `dcamera.hevc` | ドライバー／車内カメラの映像、H.265/HEVC |
| `qcamera.ts` | 道路カメラの低解像度 H.264 プレビュー |
| `rlog.zst` | ルートの完全なログ |
| `qlog.zst` | 小さく間引いたルートのログ |

comma connect に表示される映像は、低解像度の `qcamera.ts` です。フル解像度のカメラ映像は HEVC ファイルにあり、connect から手動でアップロードするか、デバイスから直接コピーする必要がある場合があります。

古いルート、古いフォーク、古いドキュメントでは、`.zst` の付かない `rlog`/`qlog` や、古い `.bz2` のログ名が出てくることがあります。現在の openpilot では、上の名前を使ってください。

## comma 3、comma 3X、comma four：何が違うのか

よく混同される別々のことが 2 つあります。カメラのハードウェアと、ファイルの構成です。

カメラのハードウェアは世代によって異なります。

| デバイス | カメラ／ストレージについて |
| --- | --- |
| comma 3 | 120 dB HDR の 1080p カメラを 3 つ搭載。コミュニティのドキュメントには、1TB、250GB、後期の 64GB、初期の 32GB といった複数のストレージ容量が載っています。 |
| comma 3X | comma 3 と同じ 3 カメラ構成で、イメージセンサーを OX03C10 に強化し、140 dB HDR。ストレージは一般に 128GB とされています。 |
| comma four | comma によれば、comma 3X と同じ処理能力、センサー構成、機能を、ずっと小さな筐体に収めたものです。3 カメラのシステムが 1.9 インチの画面の大きさに収まり、道路向きのカメラ 2 つと暗視対応の車内カメラを備えます。comma は 128GB のストレージと 10 時間分の映像としています。 |

ここでのファイルに関する説明は 3 機種すべてに当てはまります。CommaView 自体が対応しているのは comma 3X と comma four だけです。

現在の openpilot では、実際のファイル構成は comma のハードウェア間で共通です。現在のセグメントのファイルは `fcamera.hevc`、`ecamera.hevc`、`dcamera.hevc`、`qcamera.ts`、`rlog.zst`、`qlog.zst` です。

つまり、カメラが物理的に変わっても、書き出すファイルの名前は変わりません。`fcamera.hevc` は道路カメラ、`ecamera.hevc` は広角の道路カメラ、`dcamera.hevc` はドライバー／車内カメラです。

カスタムのフォークを使っている場合は、すべてのファイルがあると決めつける前に、デバイス上で確かめてください。フォークは録画の設定を変えることがあり、ドライバー／車内カメラの録画はデバイスの設定によって変わることがあります。

## ファイルはローカルのどこに保存されているのか

comma のハードウェアでは、現在の openpilot のログのルートは次のとおりです。

```text
/data/media/0/realdata
```

このフォルダーの中に、ルートのセグメントごとにタイムスタンプ付きのフォルダーができます。たとえば次のとおりです。

```text
/data/media/0/realdata/2026-05-14--12-30-05--3/
```

このフォルダーで、次のようなファイルを探します。

```text
fcamera.hevc
ecamera.hevc
dcamera.hevc
qcamera.ts
rlog.zst
qlog.zst
```

SSH/SFTP で直接作業するなら、このフォルダーから始めます。公式ドキュメントでは comma 3X や comma four に SSH で接続する方法が説明されており、openpilot はデバイス上のログのルートとして `/data/media/0/realdata` を使っています。

## 方法 1：comma connect を使う

最近のドライブなら、たいていは comma connect から始めるのがいちばん簡単です。

connect を使うのは次のような場合です。

- ルートが最近のもの
- デバイスがルートを正常にアップロードした
- プレビュー映像で足りる
- SSH ではなく Web の画面で操作したい
- 必要なのはいくつかのクリップやファイルだけ

connect は、必要なルートやセグメントの番号を多くのユーザーが最初に確認する場所でもあります。注意点は保存期間です。ローカルのデバイスがまだ削除していないルートでも、connect には表示されなくなることがあります。connect にルートが表示されなくなっても、デバイス上にファイルが残っていれば、SSH/SFTP で取り出せる場合があります。

また、connect のプレビューは `qcamera.ts` をもとにしていることも覚えておいてください。フル解像度のカメラ映像が必要なら、フルの映像ファイルがアップロードされていることを確かめるか、生の HEVC ファイルを直接取り出してください。

## 方法 2：Openpilot Toolkit を使う

Openpilot Toolkit は、ローカルでの書き出しを楽にしてくれるコミュニティ製のツールです。SSH のセットアップ、ファイルの閲覧、ドライブの映像のプレビュー、生データの書き出しといった機能があります。

Openpilot Toolkit を使うのは次のような場合です。

- GUI を使いたい
- SSH のコマンドを自分で組み立てたくない
- 鍵のセットアップに手助けが欲しい
- Windows や Android を使っている
- ルートの映像をもっと直接閲覧して書き出したい

多くのユーザーにとって、これがちょうどよい中間の選択肢です。connect より自由がきき、ターミナルでの手作業より手間がかかりません。

## 方法 3：SSH や SFTP を直接使う

SSH/SFTP を直接使う方法は、自由度がいちばん高く、手助けはいちばん少ない方法です。

大まかに言うと、SSH でアクセスするには通常次のようにします。

1. SSH 鍵を登録した GitHub アカウントを作成するか、既存のものを使います。
2. comma デバイスの設定で SSH を有効にします。
3. comma デバイスに GitHub のユーザー名を入力し、公開鍵を取得できるようにします。
4. ユーザー `comma`、ポート `22` で接続します。

接続したら、次の場所を閲覧またはコピーします。

```text
/data/media/0/realdata
```

直接アクセスを使うのは次のような場合です。

- 生の `fcamera.hevc`、`ecamera.hevc`、`dcamera.hevc` ファイルが必要
- 必要なファイルが connect に表示されない
- ルート全体をアーカイブしたい
- FileZilla や WinSCP のような SFTP クライアントに慣れている
- `ssh`、`scp`、`rsync` に慣れている

生の `.hevc` ファイルは、たいてい VLC で再生できます。ほかのアプリで MP4 が必要なら、できるだけ再エンコードではなく ffmpeg でリマックスしてください。

## どの方法を使うべきか

ドライブが最近のもので、通常のルートの確認で足りるなら、comma connect を使ってください。

SSH/SFTP の手順をすべて手作業でこなさずに、もっと扱いやすいローカルの手順を使いたいなら、Openpilot Toolkit を使ってください。

生のファイル、古いローカルファイル、ルート全体のアーカイブが必要な場合や、何をコピーするかを直接管理したい場合は、SSH や SFTP を使ってください。

## CommaView の位置付け

CommaView は、comma デバイスのカメラ配信、オーバーレイ、ランタイムのセットアップ、録画、リプレイのための、ローカルファーストの Android アプリです。

ローカルでのカメラアクセスという同じ領域に重なりますが、comma connect でも Openpilot Toolkit でも、従来のドライブレコーダーでもありません。運転支援として、あるいは車内で唯一の証拠記録システムとして使うべきではありません。

CommaView は、openpilot または[対応フォーク](/forks)（sunnypilot、StarPilot、xnor、AdventurePilot、SunnyPilot-TeslaHW1、carrotpilot）を動かしている comma 3X と comma four で動きます。comma 3 には対応していません。comma は comma 3 を、長期サポートの更新の止まった openpilot リリースに移しており、その画面から CommaView はオーバーレイを描けないためです（[理由](/ja/#faq-comma-3)）。

## 関連資料

- openpilot の公式なログのドキュメント：[Logging](https://docs.comma.ai/concepts/logs/)
- comma の公式な SSH のドキュメント：[comma 3X や comma four への接続](https://docs.comma.ai/how-to/connect-to-comma/)
- comma connect：[comma.ai/connect](https://comma.ai/connect)
- openpilot wiki：[Video Files](https://github.com/commaai/openpilot/wiki/Video-Files)
- HowToComma：[Getting Videos From Device](https://docs.howtocomma.com/docs/getting-videos-from-device)
- Openpilot Toolkit：[プロジェクトのページ](https://spektor56.github.io/OpenpilotToolkit/)
