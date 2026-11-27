---
title: "comma とフォークが対応しているか確認する"
description: "CommaView は openpilot、sunnypilot、StarPilot、xnor、AdventurePilot、SunnyPilot-TeslaHW1、carrotpilot、BluePilot、dragonpilot、OPGM に対応し、その他のフォークにもベストエフォートで対応します。"
topic: start
order: 2
kind: reference
lede: "CommaView は comma の道路カメラを、comma で動くソフトウェアの運転オーバーレイと一緒に表示します。comma 3X と comma four で openpilot と 9 つのフォークに対応し、その他の openpilot フォークにもベストエフォートで対応します。セットアップは何かを変更する前に、comma がどのフォークを動かしているかを確認します。"
updated: 2026-11-27
needs:
  - title: "comma 3X または comma four"
    text: "comma 3 には対応していません。xnor-c3 のようなフォークの comma 3 向けビルドも同様です。[comma 3 に対応していない理由](/ja/#faq-comma-3)。"
  - title: "いつもどおり動いているフォーク"
    text: "通常どおりインストールされ、動いていること。CommaView はその横にランタイムを追加するだけで、運転のしかたは一切変えません。"
steps:
  - id: unlisted
    title: "CommaView の一覧にないフォークでは、セットアップが先に確認します"
    body: |
      ガイド付きセットアップは、comma のソフトウェアがどのリポジトリからインストールされたかを確認し、そのフォーク用の CommaView のフックをインストールします。一覧にないフォークでは、何も変更せずに、まずフォークを確認します。
    tabs:
      - label: "ベストエフォート"
        body: "CommaView が表示を追加できる場合、セットアップに **CommaView はこのフォークを検証していません** と表示されます。フォークをリポジトリ名で示し、描画されるもの（カメラ、走行経路、車線、先行車、アラート、速度）と、描画されないもの（フォーク独自のボタン、色、ウィジェット）を説明します。**それでもインストール** を押すと、そのフォークにだけインストールします。**戻る** で comma の選択に戻ります。何もインストールされていません。"
        screen: setup-unlisted-fork
        pins:
          - target: install-anyway
            text: "**それでもインストール**：このフォークに CommaView の表示をベストエフォートで追加します。"
      - label: "映像のみ（早期アクセス）"
        body: "画面に CommaView の表示を追加できない FrogPilot と KisaPilot では、映像のみのフラグを持つテスターに **このフォークでは映像のみ** と表示されます。CommaView はカメラを配信し、運転データから独自の表示を描画します。フォークには何も変更を加えません。まだ comma で試されていません。フラグがない場合、セットアップはフォークに対応していないと伝え、何も変更しません。"
        screen: setup-video-only
        pins:
          - target: install-video-only
            text: "**映像のみをインストール**。"
    note: "確認でフォークが拒否された場合、セットアップは「CommaView は … に安全に表示を追加できません。」「comma では何も変更されていません。」と表示します。"
  - id: details
    title: "Live View が描画しているフォークを確認する"
    body: |
      Live View で **詳細** を開きます。**ソフトウェア** の行に comma のフォークが表示されます。CommaView の一覧にないフォークは、「crwusiz/openpilot · best effort」のようにリポジトリ名で表示されます。
    screen: phone-live-view-details
    pins:
      - target: details
        text: "映像の下の **詳細**。"
      - text: "**ソフトウェア**：comma が動かしているフォーク。"
related: [setup, overlays, uninstall]
---

## 対応フォーク

| フォーク | 入手元 | 対応開始 |
| --- | --- | --- |
| **openpilot** | comma.ai、github.com/commaai/openpilot | 最初の Beta |
| **sunnypilot** | github.com/sunnypilot/sunnypilot | 最初の Beta |
| **StarPilot** | github.com/StarPilotHQ/StarPilot（旧 github.com/firestar5683/StarPilot） | 0.0.162 |
| **xnor**（xnor と rx のビルド） | xnor-tech、github.com/xnor-tech/openpilot | 0.0.163 |
| **AdventurePilot** | github.com/AdventurePilotDev/AdventurePilot | 0.0.163 |
| **SunnyPilot-TeslaHW1** | github.com/P6g9YHK6/SunnyPilot-TeslaHW1 | 0.0.164 |
| **carrotpilot** | github.com/ajouatom/openpilot、i.carrotpilot.app からインストール | 0.0.164 |
| **BluePilot** | github.com/BluePilotDev/bluepilot | 0.0.166 |
| **dragonpilot** | github.com/dragonpilot/dragonpilot | 0.0.166 |
| **OPGM** | github.com/opgm/openpilot | 0.0.166 |

一覧にないフォークでは、CommaView が表示を追加できるかをセットアップが確認し、先にあなたに尋ねます。追加できない場合、セットアップは止まり、comma は元のままです。

## 各フォークの表示内容

### openpilot

comma.ai 自身のソフトウェアです。Live View は comma four の画面、comma 3X の画面、または CommaView 独自のオーバーレイを描画し、速度、最大、制限速度、先行車、車線変更を表示します。

### sunnypilot

CommaView は sunnypilot の画面を、sunnypilot が加えた要素と一緒に描画します。MADS のステアリングのみ・速度のみの状態、制限速度アシスト、レインボーパス、死角インジケーター、そして comma 3X の画面では制限速度標識、スマートクルーズ、開発者向け UI です。sunnypilot の設定を読み取るので、画面は comma の画面と一致します。

### StarPilot

StarPilot は運転モードを色で示し、CommaView は StarPilot が選んだ色を使います。comma four と comma 3X の画面での枠、走行経路、ウィジェット、アラート、そしてドライバーカメラを含むカメラの選択です。

StarPilot の **Disable Logging** 設定はオフにしてください。Live View の配信元であるビデオエンコーダーが止まってしまいます。

### xnor-tech の openpilot：xnor と rx

xnor-tech の openpilot には 2 つのビルドがあります。**xnor** ブランチは openpilot の画面、**rx** ブランチは sunnypilot の画面で動き、どちらも xnor-tech の車種対応を含みます。CommaView は comma で動いている方を描画し、アラートは comma が表示するとおりに示します。

rx を動かしている Rivian では、車が角度でステアリングしている間はハンドルが緑に、トルクでステアリングしている間は青になります。comma four ではハンドル、comma 3X の画面では実験モードボタンのハンドルです。

### AdventurePilot

AdventurePilot は独自の車種対応を持つ sunnypilot のフォークです。CommaView は sunnypilot の画面を、AdventurePilot が加えた要素と一緒に描画します。

- 車線中央維持のインジケーター：comma 3X の画面では押し出し量とオフセットを示すピル、comma four の画面ではコンパクトなバー。
- comma 3X の画面の CURVE チップ。カーブ速度制御が働いている間は点滅します。
- ステアリングモードに応じたハンドルの色と、Rivian が角度チャンネルでステアリングしている間の横加速度を示すトルクバー。

### SunnyPilot-TeslaHW1

SunnyPilot-TeslaHW1 は、Tesla の HW1（Autopilot 1）の車に対応する sunnypilot のフォークです。画面は sunnypilot のものなので、CommaView は sunnypilot が加えた要素をすべて含めて sunnypilot の画面を描画し、アプリではフォーク名を表示します。

CommaView のフックがインストールされている間は、このフォークの `op fork update` でフォークを切り替えられません。先に [CommaView のランタイムをアンインストール](/ja/guides/uninstall)するか、comma の画面にあるフォーク切り替え機能を使ってください。こちらは通常どおり動きます。

### carrotpilot

carrotpilot は Hyundai、Kia、Genesis の車向けの openpilot フォークで、`i.carrotpilot.app` からインストールします。CommaView はこのフォークに openpilot の画面を描画し、速度、走行経路、車線、先行車を表示します。carrotpilot が自身の画面に加えるナビ、速度取締カメラ、HUD などはまだ描画しません。

carrotpilot の自動アップデートと、Web ページにある Git ツールは、comma が再起動するまで CommaView のフックを外してしまいます。アプリが再起動を求め、再起動後に Live View が戻ります。

### BluePilot、dragonpilot、OPGM

CommaView 0.0.166 とそのランタイムから一覧に加わりました。CommaView はそれぞれのフォーク名を表示し、ベースとなるソフトウェアの見た目で描画します。BluePilot は sunnypilot、dragonpilot と OPGM は openpilot として描画し、dragonpilot の ALKA はステアリングとして表示します。いずれかをベストエフォートで動かしていた comma は、ランタイムのアップデート後の起動時に一覧のフォークとして扱われるようになります。どれもまだ CommaView を使って走行したことはありません。CommaView 公式の[オーバーレイパック](/ja/guides/overlays)を使うと、BluePilot と dragonpilot 独自の画面をさらに多く描画できます。

## CommaView の一覧にないフォーク

CommaView 0.0.165 以降、そのランタイムが comma にあれば、セットアップは一覧にない openpilot フォークにもベストエフォートで CommaView の表示を追加できます。Live View はフォークを openpilot の見た目で描画し、sunnypilot の画面をベースにしたフォークなら sunnypilot の見た目で描画します。元に戻すには、デバイス設定の **ランタイムをアンインストール** でフォークのファイルを元の状態に戻します。

- **ベストエフォート。** CommaView のリリースは、あなたのフォークではテストされていません。フォークが CommaView の追従できない形に自動でアップデートされた場合、CommaView の表示はオフになり、CommaView のリリースが変更に対応するまで、フォークはいつもどおり運転し、自身の画面を表示します。
- **すべてのフォークではありません。** openpilot の古いネイティブ画面をベースにしたフォークには対応していません（下記）。
- **同意はそのフォークに対してのみ有効です。** comma が一覧にない別のフォークに切り替わった場合、CommaView はそこに表示を追加する前に、セットアップでもう一度尋ねます。

### インストールチェックを通過したフォーク（ベストエフォート）

以下はいずれも **CommaView のインストールチェックを通過しましたが、ベストエフォートであり、車ではテストしていません。** 2026 年 11 月に、記載のブランチについて、CommaView 0.0.165 がインストールするランタイムで確認しました。インストーラーがフォークを提示し、同意すると CommaView の表示を追加して確認する、という流れを comma 上と同じように行っています。いずれも車内の comma では試しておらず、フォークが両方のデバイスですべての車に対応しているとは限りません。また、フォークの次のアップデートで結果が変わることがあります。

| フォーク | 確認したブランチ | デバイス | 描画 |
| --- | --- | --- | --- |
| **crwusiz**（github.com/crwusiz/openpilot） | master_c4、master_c3 | comma four、comma 3X | openpilot |
| **jixiexiaoge’s Carrot**（github.com/jixiexiaoge/openpilot） | Carrot | comma four、comma 3X | openpilot |
| **MoreTore**（github.com/MoreTore/openpilot） | release-mici | comma four | openpilot |
| **zoompilot**（github.com/zoompilot/zoompilot） | main | comma four、comma 3X | sunnypilot |
| **AlexandreSato**（github.com/AlexandreSato/openpilot） | master | comma four、comma 3X | openpilot |
| **lukasloetkolben**（github.com/lukasloetkolben/openpilot） | master | comma four、comma 3X | openpilot |
| **mvl-boston**（github.com/mvl-boston/openpilot） | master、0111-op-honda | comma four、comma 3X | openpilot |
| **mouxangithub**（github.com/mouxangithub/openpilot） | master-c3 | comma four、comma 3X | sunnypilot |
| **programanichiro**（github.com/programanichiro/openpilot） | release-piZ2 | comma four、comma 3X | openpilot |
| **infiniteCable2**（github.com/infiniteCable2/openpilot） | master | comma four、comma 3X | sunnypilot |
| **herizon1054**（github.com/herizon1054/openpilot） | dplcc | comma four、comma 3X | openpilot |
| **NotAutopilot**（github.com/NotAutopilot/openpilot） | nap-release、naponsp-alpha | comma four、comma 3X | openpilot（nap-release）、sunnypilot（naponsp-alpha） |

あなたのフォークが載っていませんか？ それでも動く可能性があります。セットアップは何かを変更する前にフォークを確認します。

### 対応していないフォーク

以下のフォークは画面に CommaView の表示を追加できないため、セットアップはその旨を伝え、comma では何も変更しません。

- **FrogPilot**（github.com/FrogAi/FrogPilot）。openpilot の古いネイティブ（Qt）画面で動いており、CommaView の表示を入れる場所がありません。映像のみは早期アクセス中です。
- **KisaPilot**（github.com/kisapilot/openpilot）。Python の画面がオフになっており、openpilot の古いネイティブ（Qt）画面で動いています。映像のみは早期アクセス中です。
- **IQ.Pilot**（github.com/IQLvbs/iqpilot）。2026 年 10 月から独自の IQ.OS で動いています。CommaView が独立したフォークとして対応できるようになるまで、対応は保留です。
- **hikee9123**（github.com/hikee9123/openpilot）。openpilot の古いネイティブ（Qt）画面で動いています。

**早期アクセス：FrogPilot と KisaPilot 向けの映像のみ。** 映像のみのフラグがあると、セットアップはこれらのフォークのカメラを、フォーク独自の画面の代わりに CommaView 独自のオーバーレイで Live View に表示することを提案します。フォークには何も変更を加えません。まだ comma で試されていません。フラグがない場合、セットアップは引き続き対応していないと伝え、何も変更しません。

## 対応する comma デバイス

comma 3X と comma four です。comma 3 には対応していません。xnor-c3 のようなフォークの comma 3 向けビルドも同様です：[comma 3 に対応していない理由](/ja/#faq-comma-3)。アプリは Android のスマートフォン、タブレット、カーナビで動きます。

## リリースブランチと開発ブランチ

各リリースの前に、CommaView のランタイムをこれらのフォークのリリースビルドに対してビルドし、確認しています。openpilot の nightly と sunnypilot の dev ブランチは、早期警告として、変更があった日ごとに確認しています。開発ブランチは CommaView より速く変わることがあります。変更によって CommaView のフックが読み込まれなくなっても、フォークの画面と運転はいつもどおり続きます。

## あなたのフォークが載っていない場合

ベストエフォートで試してみてください。一覧への追加は [my.commaview.com](https://my.commaview.com) の機能リクエストボードで依頼するか、アプリからアイデアを送ってください（設定 › **サポートと診断**）。一覧にあるフォークは各リリースの前に確認されます。各リリースの[新機能](/whats-new)もご覧ください。

## よくある質問

**CommaView はフォークの運転のしかたを変えますか？** いいえ。フォークの横に小さなランタイムを、画面の UI に小さなフックを追加するだけで、CommaView が同じ走行経路、車線、アラートを描画できるようにします。車の運転のしかたは変わりません。

**CommaView は StarPilot で動きますか？** はい、CommaView 0.0.162 から対応しています。Live View には StarPilot 独自の色、ウィジェット、カメラの選択が表示されます。StarPilot の **Disable Logging** 設定はオフにしてください。CommaView の配信元であるビデオエンコーダーが止まってしまいます。

**CommaView は carrotpilot で動きますか？** はい、CommaView 0.0.164 から対応しています。Live View は openpilot の画面を描画します。carrotpilot が自身の画面に加えるナビや速度取締カメラなどは、まだ描画しません。carrotpilot が自動でアップデートした後は、アプリが再起動を求め、再起動すると Live View が戻ります。

**CommaView は FrogPilot で動きますか？** まだです。openpilot の古いネイティブ（Qt）画面で動いており、CommaView の表示を入れる場所がないため、セットアップは対応していないと伝え、何も変更しません。FrogPilot と KisaPilot 向けの映像のみは、テスター向けに早期アクセス中です。
