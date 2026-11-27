---
title: "comma から CommaView を削除する"
description: "デバイス設定で comma から CommaView ランタイムをアンインストールし、フォークのファイルを元に戻し、スマートフォンから comma を削除します。"
topic: account
order: 3
kind: walkthrough
lede: "**ランタイムをアンインストール** は comma から CommaView を削除します。CommaView のフックを元に戻し、ランタイムを止め、`/data/commaview` を削除します。フォークはこれまでどおり運転を続けます。CommaView を削除するときや、ガイド付きセットアップを最初からやり直すときに使います。"
parked: true
updated: 2026-11-27
needs:
  - title: "スマートフォンと comma が一緒にあること"
    text: "comma と同じ Wi‑Fi か、comma のテザリングにつながっていること。デバイス設定でアップデートや削除を行うには comma が必要です。"
  - title: "車の電源が入っていて P レンジ"
    text: "車が走行中なら、comma は openpilot が解除されて P レンジに入るまでアンインストールを待機させます。"
steps:
  - id: device-settings
    title: "comma のデバイス設定を開く"
    body: |
      ホームから comma の **デバイス設定** を開き、**ランタイム**（「アップデートまたは削除」）を開きます。
    screen: device-settings
    pins:
      - target: runtime-row
        text: "**ランタイム**：CommaView のアップデートまたは削除。"
  - id: uninstall
    title: "「ランタイムをアンインストール」をタップする"
    body: |
      ランタイムのアップデートの下にある **ランタイムをアンインストール** で、この comma から CommaView を削除します。その後、ガイド付きセットアップを最初から実行できます。
    screen: device-runtime
    pins:
      - target: uninstall
        text: "**ランタイムをアンインストール**。"
  - id: confirm
    title: "確認する"
    body: |
      **CommaView が削除されます**：CommaView はランタイムのフックを元に戻して停止し、この comma から `/data/commaview` を削除します。comma はスマートフォンに保存されたままです。短いカウントダウンが終わったら **ランタイムをアンインストール** をタップします。
    screen: runtime-uninstall-confirm
    pins:
      - target: removed
        text: "**CommaView が削除されます** と、その内容。"
      - text: "カウントダウンの後に **ランタイムをアンインストール**。**キャンセル** で CommaView を残します。"
    note: "車が走行中なら、comma はアンインストールを待機させます。openpilot を解除して車が P レンジに入ると CommaView が削除され、それまでは動き続けます。"
  - id: forget
    title: "必要ならスマートフォンから comma を削除する"
    body: |
      デバイス設定に、ランタイムが削除されたことが表示されます。スマートフォンからも comma を外すには、デバイス設定の最後にある **この comma を削除** をタップします。CommaView にこの comma が表示されなくなり、ペアリングの鍵が削除されます。アプリ自体を削除するには、ほかのアプリと同じように Android の設定から CommaView をアンインストールしてください。
    screen: device-settings-forget
    pins:
      - target: forget-row
        text: "**この comma を削除**。"
check: "ダイアログに **ランタイムをアンインストールしました** と表示され、デバイス設定のランタイムに **削除済み** と表示されます：「comma から CommaView がアンインストールされました。もう一度インストールするには、ガイド付きセットアップを実行してください。」"
fixes:
  - q: "「SSH の権限エラーのため、アンインストールに失敗しました。」"
    a: "comma がこのスマートフォンの SSH 接続を受け入れませんでした。comma の **設定 → デバイス → SSH** で SSH がオンになっていること、その GitHub ユーザー名にこのスマートフォンの鍵があることを確認してから、**もう一度アンインストール** をタップしてください。"
  - q: "「comma は CommaView をアンインストールできなかったため、元のままにしました」"
    a: "何も削除されていません。車を P レンジに入れて、もう一度お試しください。"
  - q: "「車が P レンジに入るまでアンインストールを待機しています。」"
    a: "車が走行中です。openpilot を解除して P レンジに入れ、電源を入れたままにしておけば、comma が自動で CommaView を削除します。"
  - q: "アンインストールのボタンが淡色表示になっている"
    a: "CommaView はすでにランタイムのアップデートかアンインストールを実行中です。終わってからもう一度お試しください。"
related: [setup, update-runtime, forks]
---

## アンインストールで元に戻るもの

- **一覧にあるフォーク** では、CommaView がフォークの画面の UI に加えた小さなフックを元に戻します。
- **CommaView の一覧にないフォーク**（ベストエフォート）では、フォークのファイルを元の状態に戻します。
- **映像のみ** はフォークのファイルを何も変更していないので、アンインストールではランタイムを削除します。

SunnyPilot-TeslaHW1 では、`op fork update` の前にランタイムをアンインストールしてください。CommaView のフックがインストールされている間は、フォークを切り替えられません。詳しくは[comma とフォークが対応しているか確認する](/ja/guides/forks)をご覧ください。

## CommaView をもう一度セットアップする

アンインストール後も、comma はスマートフォンに保存されたままです。[ガイド付きセットアップ](/ja/guides/setup)を実行すると、新規インストールとしてもう一度インストールできます。
