---
title: "Android での comma カメラのローカル配信：CommaView ができること"
description: "CommaView は、comma の道路カメラを運転オーバーレイ付きで、自分のネットワーク経由で Android に配信します。Live View、録画、ライブ配信、そしてできないこと。"
date: 2026-11-06
slug: local-comma-camera-streaming-android
tags:
  - comma camera streaming
  - comma four
  - Android app
  - CommaView
  - local streaming
heroLabel: "製品の適性"
draft: false
---

CommaView は、comma の道路カメラを運転オーバーレイ付きで、自分のネットワーク経由で Android のスマートフォン、タブレット、カーナビに配信します。comma とスマートフォンの間にクラウドは入らず、先にアップロードする必要もありません。

構成は 2 つです。CommaView アプリと、comma 上でカメラと運転データをアプリに送る小さなランタイム `commaviewd` です。ガイド付きセットアップがランタイムをインストールし、確認まで行います。

## そもそもなぜ配信するのか

comma four の画面は 1.9 インチです。役目は果たしていますが小さく、オーナーもそう言っています。comma で映像を見るほかの方法は、別の目的のために作られています。

- **comma connect** は、アップロードしたドライブを 3 日間、comma prime なら 1 年間保存します（[comma.ai/prime](https://comma.ai/prime)）。[openpilot 0.11.2](https://blog.comma.ai/0112release/) からは、comma power を取り付けていれば、駐車中に道路カメラとドライバーカメラをインターネット経由でライブ配信でき、comma 上で MP4 クリップを切り出せます。
- **SSH** では、comma のストレージから 1 分ごとの生の HEVC セグメントを取り出せます。

どちらも、運転中に openpilot の運転オーバーレイ付きで道路を見せてはくれません。CommaView はそのためのものです。

## CommaView ができること

### Live View

道路カメラのライブ映像に、お使いのフォーク自身の画面を重ねて描きます。comma four の画面、comma 3X の画面、または CommaView 独自の画面で、速度、MAX、制限速度、先行車、車線変更を 1 つのクラスターにまとめます。Live View は各フォークの画面を、sunnypilot の MADS から StarPilot 独自の HUD まで、そのフォークが加えた要素ごと描きます。comma の最大 20 フレーム／秒で動き、ピクチャー・イン・ピクチャーでも動き続けます。

タブレットや Android カーナビでは、CommaView はダッシュボードのようにレイアウトされ、Live View の操作ボタンは運転席側に並びます。

### 録画

Live View で「録画」をタップすると、駐車後に CommaView がその区間の comma 自身の映像を最大 10 分ダウンロードし、スマートフォン上でフォークの画面を重ねて描きます。これがリプレイです。再生、共有、ほかのアプリで開くことができます。ライブコピーは、運転中に Live View が表示しているものを 720p または 1080p で保存し、停車した瞬間に使えます。10 分の制限もありません。録画は削除するまでスマートフォンに残ります。

### ライブ配信

ライブ配信は、Live View が表示しているもの（道路と CommaView のオーバーレイ）を、YouTube チャンネルや任意の RTMP サーバーに 720p または 1080p で配信します。一度 YouTube でログインすれば、配信ごとに作成、開始、終了まで行います。配信は限定公開で始まります。視聴者には、あなたがどこを走っているかがわかります。

### ペアリングしたスマートフォンだけに

comma のカメラとデータは、ペアリングしたスマートフォンとカーナビにだけ届きます。映像、ドライブ、場所は comma からスマートフォンへ送られるだけで、あなたが送信、配信、提供しない限り、ほかには送られません。

## インターネットが必要なもの

Live View と録画には不要です。同じローカルネットワーク上で、comma からスマートフォンへ直接届きます。そのネットワークは Wi-Fi でも、スマートフォン、カーナビ、AI ボックス、comma のいずれかが車内で作るテザリングでもかまいません。ログイン、アプリとランタイムのアップデート、車両の位置の地図、ランキング、ライブ配信、CommaView への送信にはインターネットが必要です。

## 対応しているもの

comma 3X と comma four で、openpilot、sunnypilot、StarPilot、xnor-tech の openpilot、AdventurePilot、SunnyPilot-TeslaHW1、carrotpilot に対応しています。そのほかの openpilot フォークはベストエフォートで動きます。セットアップがフォークを確認し、インストールする前に確認を求めます。comma 3 には対応していません。comma 3 は更新の止まった openpilot リリースで動いており、その画面から CommaView はオーバーレイを描けないためです。[対応フォーク](/forks)。

Android 8 以降の Android スマートフォン、タブレット、カーナビが必要です。

## CommaView ではないもの

- **comma connect ではありません。** ドライブをクラウドに保存したり、離れた場所から車を見たりはできません。それには connect を使ってください。
- **ドライブレコーダーではありません。** 事故や駐車中の証拠になる映像が必要なら、[専用のドライブレコーダーを使ってください](/ja/blog/is-comma-a-dashcam)。
- **運転支援や安全システムではありません。** comma が見ているものを表示するだけです。正しいのは実際の道路です。

## 安全に使うために

CommaView のセットアップは駐車中に行ってください。運転中に Live View を見るのは同乗者にしましょう。一人で運転するときは comma 自身の画面と同じように扱い、目は道路から離さないでください。

CommaView は招待制の Beta です。[リストに登録](https://my.commaview.com/join)すると、順番が来たときにメールでお知らせします。

CommaView は非公式であり、comma.ai、sunnypilot、対応する openpilot フォークのいずれとも関係がなく、承認も受けていません。Beta 版のソフトウェアであり、安全システムではありません。運転から注意をそらさないでください。
