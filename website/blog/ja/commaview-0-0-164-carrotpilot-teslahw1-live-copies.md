---
title: "CommaView 0.0.164：carrotpilot、SunnyPilot-TeslaHW1、ライブコピー"
description: "CommaView 0.0.164 は carrotpilot と SunnyPilot-TeslaHW1 に対応し、運転中に Live View の表示を保存するライブコピーを追加しました。ナビと Surround の早期アクセスも。"
date: 2026-10-22
slug: commaview-0-0-164-carrotpilot-teslahw1-live-copies
tags:
  - openpilot forks
  - carrotpilot
  - SunnyPilot-TeslaHW1
  - Tesla
  - Hyundai
  - recordings
heroLabel: "リリースノート"
draft: false
---

CommaView 0.0.164 を Beta の全員に公開しました。openpilot フォークが新たに 2 つ、**carrotpilot** と **SunnyPilot-TeslaHW1** に対応し、CommaView が動くのは openpilot、sunnypilot、StarPilot、xnor-tech の openpilot、AdventurePilot、SunnyPilot-TeslaHW1、carrotpilot の 7 つになりました。また、運転中に Live View が表示しているものを保存し、停車した瞬間に使える **ライブコピー** も加わりました。

ランタイム `v0.0.60-beta` が同梱されており、新しい 2 つのフォークを認識します。アプリが案内したらアプリからランタイムをアップデートし、求められたら comma を再起動してください。

## SunnyPilot-TeslaHW1

SunnyPilot-TeslaHW1 は、Tesla の HW1（Autopilot 1）車に対応した sunnypilot のフォークです。画面は sunnypilot のものなので、CommaView は sunnypilot が加えた要素も含めて sunnypilot の画面を描き、アプリ内にフォーク名を表示します。

注意点が 1 つあります。CommaView のフックが入っている間は、このフォークの `op fork update` でフォークを切り替えられません。先に CommaView をアンインストールするか、comma の画面にあるフォーク切り替えを使ってください。こちらは通常どおり動きます。

## carrotpilot

carrotpilot は、Hyundai、Kia、Genesis の車向けの openpilot フォークで、`i.carrotpilot.app` からインストールします。CommaView は carrotpilot に対して openpilot の画面を描き、速度、走行経路、車線、先行車を表示し、アプリ内にフォーク名を表示します。

現時点では制限が 2 つあります。

- **carrotpilot 独自の画面はまだ描きません。** carrotpilot が openpilot の画面に加えるもの（ナビ、速度取締りカメラ、HUD など）は Live View に表示されません。
- **carrotpilot のアップデートは、comma が再起動するまで CommaView のフックを外します。** carrotpilot の自動アップデートや、Web ページの Git ツールは、動作中にファイルをリセットします。壊れるものはありません。アプリが再起動を求め、再起動後に Live View が戻ります。

## ライブコピー

これまで「録画」はリプレイを作るものでした。駐車後、アプリが comma 自身の映像をダウンロードし、その上に HUD を描きます。画質は今もこれが一番ですが、走行後しばらく時間がかかり、1 回の録画は 10 分までです。

設定 › 録画 › **Live View での録画** で、「録画」が何を作るかを選べるようになりました。

| 選択肢 | できるもの |
| --- | --- |
| リプレイ（デフォルト） | comma 自身の映像に HUD を重ねたもの。駐車後に作成します。最高の画質で、1 回の録画は最大 10 分。 |
| ライブコピー | 運転中に Live View が表示しているもの。スマートフォンに保存され、停車した瞬間に録画で使えます。10 分の制限はありません。 |
| 両方 | すぐにライブコピー、走行後にリプレイ。 |

ライブコピーは 720p（1 時間あたり約 1.4 GB）または 1080p（1 時間あたり約 2.3 GB）、20 フレーム／秒です。アプリを切り替えたりスマートフォンをロックしたりしても続き、通知から停止できます。スマートフォンのストレージがなくなる前にきちんと停止し、録画中にアプリが閉じても、最後の 1 分以外はすべて残ります。

ライブコピーはスマートフォンに残り、アップロードされることはありません。

## 0.0.164 のその他の変更

- **画面全体を使う設定。** 録画、表示、ライブ配信の各ページがオフライン地図と同じレイアウトになり、収まる場合は 2 列で表示されます。タブレット、カーナビ、横向きのスマートフォンでも揃って表示されます。
- **インストールに失敗した理由。** セットアップ、ランタイムのアップデート、アンインストールが失敗すると、何が起きたか、どうすればよいかをアプリが伝えます。CommaView が対応していないフォーク、車が走行中、comma がインターネットにつながっていない、ダウンロードが壊れている、などです。comma が元の状態に戻されたかどうかも表示し、「詳細をコピー」でサポートに必要なレポートをコピーできます。
- **リプレイの高速化。** リプレイは表示する部分の映像だけをダウンロードし、1 つ作成している間にキューの次のドライブをダウンロードします。アプリの終了、10 分の制限、車の電源オフで途中で切れた録画も、リプレイにできるようになりました。
- **リプレイの画質設定が再び機能。** Balanced、High、Max で、再び異なるリプレイが作られます。これまではすべてのリプレイが同じ 40 Mbit/s で作られていました。デフォルトの High では、comma 3X のファイルサイズが約半分になります。

## 早期アクセス：ナビと Surround

一部の機能は開発の初期段階にあります。**ナビ**、**Surround**、**ライブ配信**、**CommaView に送信** です。フィードバックを集める間、機能フラグを使って限られたテスターにだけ公開しているので、有効になっているアカウントでのみ表示されます。

- **ナビ** は、ホームから Live View までのターンバイターン案内です。場所を検索してルートを選び、曲がり角のカード、音声案内、そして CommaView の画面では車線に描かれる矢印に従います。曲がる場所を間違えても、数秒で新しいルートを見つけます。表示のみの機能で、comma や車には何も送りません。
- **Surround** は、車の周りの道路を 3D で見せる表示です。カメラが見ている道路を車線や交差点ごと描き、周りの乗用車、トラック、信号も表示します。

ナビのルート検索など、一部は有料サービスで動いているため、通常の使い方でどれだけ費用がかかるかわかるまで、グループを小さくしています。テストに協力したい方は、[Discord](https://discord.gg/UuMhz9K8ft) でご連絡ください。実際のドライブでどう動いたかを教えていただけると助かります。

## 入手方法

CommaView は招待制の Beta です。参加している方には、アプリが 0.0.164 のアップデートを自動で案内します。アップデートしたら、アプリから comma のランタイムをアップデートし、求められたら comma を再起動してください。ランタイムのアップデートは、車が P レンジで openpilot が解除されているときまで待つので、走行が中断されることはありません。

CommaView が初めての方は、[セットアップガイド](/ja/guides/setup)でアプリのインストールから comma の接続までを順に説明しています。

## 関連記事

- [CommaView で使える openpilot フォーク](/forks)（[SunnyPilot-TeslaHW1](/forks#teslahw1) と [carrotpilot](/forks#carrotpilot) を含む）
- 各リリースの[新機能](/whats-new)
- [CommaView のリリースのしくみ](/ja/guides/releases)

CommaView は非公式であり、comma.ai、sunnypilot、carrotpilot、SunnyPilot-TeslaHW1 とは関係ありません。Beta 版のソフトウェアであり、安全システムではありません。運転から注意をそらさないでください。
