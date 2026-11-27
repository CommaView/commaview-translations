---
title: "CommaView が StarPilot、xnor、AdventurePilot に対応"
description: "CommaView 0.0.163 は、0.0.162 の StarPilot に続いて xnor-tech の openpilot と AdventurePilot に対応しました。各 openpilot フォークが comma 3X と comma four の Live View で何を表示するかを紹介します。"
date: 2026-10-12
slug: commaview-starpilot-xnor-adventurepilot
tags:
  - openpilot forks
  - StarPilot
  - sunnypilot
  - xnor
  - AdventurePilot
  - Rivian
heroLabel: "リリースノート"
draft: false
---

CommaView は、5 つの openpilot ビルドで動くようになりました。**openpilot**、**sunnypilot**、**StarPilot**、**xnor-tech の openpilot**（xnor と rx の 2 つのビルド）、そして **AdventurePilot** です。StarPilot は CommaView 0.0.162 で加わり、0.0.163 Beta で xnor と AdventurePilot が加わりました。どのフォークでも、Live View はそのフォーク自身の画面を、フォークが追加した要素ごと、Android のスマートフォン、タブレット、カーナビに描きます。

これまで、これらのフォークではセットアップが「unsupported upstream remote」で止まっていました。0.0.163 のアプリとそのランタイムなら、openpilot と同じようにインストールしてペアリングできます。

## 各フォークが Live View で表示するもの

CommaView はフォークの名前から推測しません。comma 上のランタイムがフォークの画面に何が加わっているかをアプリに伝え、アプリはそれを comma four の画面、comma 3X の画面、または CommaView 独自の画面に描きます。

| フォーク | CommaView が描くもの |
| --- | --- |
| openpilot | comma four と comma 3X の画面、または CommaView 独自のオーバーレイ |
| sunnypilot | sunnypilot の画面：MADS、制限速度アシスト、虹色の走行経路、死角インジケーター、comma 3X 向けの追加要素 |
| StarPilot | StarPilot の色、ウィジェット、アラート、カメラの選択 |
| xnor | xnor ビルドでは openpilot の画面、rx では sunnypilot の画面、そして rx の Rivian 向けハンドルの色 |
| AdventurePilot | sunnypilot の画面に、車線センタリングインジケーター、CURVE チップ、ステアリングモードの色を加えたもの |

## StarPilot

StarPilot は運転モードを色で示します。CommaView は StarPilot が選んだ色をそのまま使います。枠、走行経路、ウィジェット、アラート、そしてドライバーカメラを含むカメラの選択です。先に StarPilot の **Disable Logging** 設定をオフにしてください。この設定は、Live View が配信に使う映像エンコーダーを止めてしまいます。

## xnor-tech の openpilot：xnor と rx

xnor-tech の openpilot には、1 つのリポジトリから 2 つのビルドがあります。**xnor** ブランチは openpilot の画面を、**rx** ブランチは sunnypilot の画面を使い、どちらにも xnor-tech の車種対応が入っています。CommaView は comma がどちらを動かしているかを判別してその画面を描き、アラートも comma が書くとおりに表示します。

rx を動かしている Rivian では、ハンドルの色が車のステアリング方式を示します。角度で操舵しているときは緑、トルクで操舵しているときは青です。CommaView は同じ色を、comma four のハンドルと comma 3X の実験モードボタンに描きます。

## AdventurePilot

AdventurePilot は、独自の車種対応を持つ sunnypilot のフォークです。CommaView は sunnypilot の画面に、AdventurePilot が加えた要素を描きます。

- **車線センタリングインジケーター**：comma 3X の画面では押し込みとオフセットを示すピル、comma four の画面ではコンパクトなバー。
- comma 3X の画面の **CURVE チップ**：カーブ速度制御が作動している間、点滅します。
- ハンドルの **ステアリングモードの色**、そして Rivian が角度チャンネルで操舵している間の横加速度を示すトルクバー。

## 入手方法

CommaView は招待制の Beta です。参加している方には、アプリが 0.0.163 のアップデートを自動で案内します。アプリをアップデートしたら、アプリから comma のランタイムをアップデートし、求められたら comma を再起動してください。ランタイムのアップデートは、車が P レンジで openpilot が解除されているときまで待つので、走行が中断されることはありません。

CommaView が初めての方は、[セットアップガイド](/ja/guides/setup)でアプリのインストールから comma の接続までを順に説明しています。

## 変わらないこと

- CommaView は **comma 3X** と **comma four** で動きます。comma 3 には引き続き対応していません。xnor-c3 のようなフォークの comma 3 向けビルドも同様です（[理由](/ja/#faq-comma-3)）。
- CommaView がフォークの運転のしかたを変えることはありません。小さなランタイムを横に置き、画面表示の UI に小さなフックを入れるだけで、同じ走行経路、車線、アラートを描けるようにしています。
- CommaView がまだ対応していないフォークでは、セットアップは止まり、comma は元の状態のまま残ります。my.commaview.com の機能リクエストボードで、お使いのフォークへの対応をリクエストできます。

## 関連記事

- [CommaView で使える openpilot フォーク](/forks)と、それぞれが表示するもの
- 各リリースの[新機能](/whats-new)
- [CommaView のリリースのしくみ](/ja/guides/releases)

CommaView は非公式であり、comma.ai、sunnypilot、StarPilot、xnor-tech、AdventurePilot とは関係ありません。Beta 版のソフトウェアであり、安全システムではありません。運転から注意をそらさないでください。
