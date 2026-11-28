---
title: "Android AI ボックスで CommaView を使う"
description: "Android AI ボックスで、車の CarPlay や Android Auto の画面に Live View を表示します。差し込み、CommaView のインストール、comma のネットワークへの接続、ペアリング、画面合わせ。"
topic: screens
order: 4
kind: walkthrough
lede: "車に純正の **有線** CarPlay または Android Auto があれば、**Android AI ボックス** で CommaView の Live View を車の画面に表示できます。オーディオの交換も配線も不要です。ボックスは、スマートフォンを差し込む USB ポートにつなぐ小型の Android コンピューターです。CommaView はボックス上で動くので、スマートフォンは通話や地図に使えます。"
parked: true
updated: 2026-11-27
needs:
  - title: "有線の CarPlay または Android Auto"
    text: "純正の有線 CarPlay か有線 Android Auto で、データを通す USB ポートがあること。ボックスが車の方式に対応しているか確認してください。"
  - title: "本物の Android が動くボックス"
    text: "Android 8 以降で、ファイルからアプリをインストールできること。閉じた「動画」ボックスや単なるワイヤレスアダプターでは CommaView は動きません。[どのボックスを買うか](/ja/blog/android-ai-box-commaview)。"
  - title: "スマートフォンの CommaView"
    text: "先にスマートフォンから comma をセットアップし、その後でボックスをペアリングします。[CommaView をセットアップ](/ja/guides/setup)。"
howItWorks:
  - title: "comma"
    text: "ローカルネットワークで Live View をボックスに送ります。"
    edge: "Wi‑Fi"
  - title: "AI ボックス"
    text: "ほかの Android デバイスと同じように CommaView を動かします。"
    edge: "USB"
  - title: "車の画面"
    text: "CarPlay を表示するのと同じように、ボックスの画面を表示します。"
steps:
  - id: plug-in
    title: "ボックスを差し込み、CommaView をインストールする"
    body: |
      ボックスを車の CarPlay または Android Auto の USB ポートに差し込み、起動させます。ひとまず、インターネットにつながる Wi‑Fi に接続します。

      ボックスのブラウザで、招待が届いたメールアドレスを使って [my.commaview.com](https://my.commaview.com) にログインし、**Get the app** の下の **Download CommaView** をタップします。このインストールのためにブラウザからのインストールを許可し、終わったら元に戻します。CommaView を開いてログインします。
    note: "CommaView はボックスの Android モードで動かしてください。スマートフォンの CarPlay を中継するモードではありません。"
  - id: network
    title: "ボックスと comma を同じネットワークにつなぐ"
    body: |
      Live View はインターネットではなく、ローカルネットワークを通って comma からボックスに直接届きます。両方がつながっているネットワークなら何でも構いません。
    tabs:
      - label: "ボックスのテザリング"
        body: "SIM カード付きのボックスは、たいていテザリングを共有できます。オンにして、comma の **設定 › ネットワーク** で comma を参加させます。"
      - label: "スマートフォンのテザリング"
        body: "ボックスと comma をスマートフォンのテザリングに参加させます。どちらもそこからインターネットを使えます。"
      - label: "comma のテザリング"
        body: "comma のテザリングをオンにして、ボックスから参加します。"
    note: "多くのボックスはワイヤレス CarPlay のためにスマートフォンとの接続にも Wi‑Fi を使い、その間は Wi‑Fi のインターネットが切れるものもあります。ボックスの VPN はオフにしてください。"
  - id: pair
    title: "ボックスを comma とペアリングする"
    body: |
      スマートフォンで comma の **デバイス設定** を開き、**別のスマートフォンをペアリング** をタップして、**別のスマートフォンを追加** の下の **招待を表示** をタップします。ボックスで **CommaView を実行している comma をペアリング** をタップし、comma を選んで、コードを入力するか **QR コードをスキャン** をタップします。すべての手順は[タブレットや車の画面で CommaView を使う](/ja/guides/car-screens#step-pair)にあります。
  - id: edges
    title: "車が切り取る端からアプリを内側に寄せる"
    body: |
      車によっては、ボックスが送る映像の端を切り取ってしまい、Android はそれを検知できません。**設定 › 表示 › 画面の端** を開きます。アプリの端を示す線が表示されるので、線が一周すべて見えるまで **−** と **+** で各辺を内側に動かし、**完了** をタップします。**リセット** でオフにできます。

      その後、ホーム、Live View、設定が内側に収まっているか確認します。
    screen: settings-screen-edges
    pins:
      - target: done
        text: "**−** と **+** で各辺を内側に動かし、**完了** で保存します。"
      - text: "同じく **設定 › 表示** にある **テーマ**：**この端末と同じ** でボックスに合わせます。"
  - id: auto
    title: "自動で開くようにする"
    body: |
      **設定 › 表示** の **Live View を開いています** で：

      - **このデバイスの起動時に CommaView を開く**：車と一緒に再起動するボックス向け。
      - **Bluetooth 接続時に自動で開く**：スマートフォンを選びます。再起動せずスリープするボックス向け。
      - **接続したら Live View を開く**：車の電源が入った状態で comma が接続したら、すぐに Live View に入ります。

      CommaView が自動で開けるよう、**他のアプリの上に重ねて表示** を許可してください。許可しない場合は、開くかどうかを通知で尋ねます。
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**接続したら Live View を開く**。"
  - id: check
    title: "Live View の再生を確認してから運転する"
    body: |
      車の電源を入れた状態で、ボックスで Live View を開きます。操作ボタンは運転席側のレールに並び、縦の短い画面ではコンパクトになります。運転する前に、映像が再生され、何も切れていないことを確認してください。
    screen: ai-box-live-view
    pins:
      - target: record-button
        text: "レールの上端の **録画**。"
      - target: details
        text: "レールの下の方の **詳細**。"
    note: "ボックスの画面は映像として車に届くため、Live View は途中でもう一度エンコードされます。手に持ったスマートフォンより、少しぼやけて少し遅れると考えてください。"
check: "車の画面に CommaView のホームが表示され、続いて Live View が表示されて配信状態のピルに **ライブ** と表示されます。**画面の端** の線が一周すべて見えています。"
fixes:
  - q: "ボックスに CommaView をインストールできない"
    a: "ボックスによっては、ブラウザからのインストールがブロックされます。パソコンでアプリをダウンロードし、USB メモリーでコピーして、ボックスのファイルマネージャーから開いてください。システムが閉じていてアプリの一覧が固定されたボックスには、インストールできません。"
  - q: "ボックスが comma を見つけられない"
    a: "両方が同じネットワークにあること、ボックスがワイヤレス CarPlay のために Wi‑Fi を切っていないことを確認してください。必要なら comma の IP アドレスを入力します。comma 自身のテザリングでは 192.168.43.1 です。詳しくは[車内で接続する](/ja/guides/connect-in-the-car)をご覧ください。"
  - q: "映像がカクつく、または再生されない"
    a: "comma は道路カメラを 1928 × 1208 の HEVC（H.265）で送るため、安価なボックスのデコーダーでは力不足のことがあります。デコーダーが失敗すると、CommaView はボックスのほかのデコーダーを自動で試します。どれも使えない場合、Live View に **この comma の映像を再生できません** と表示されます。ボックスからサポートに報告を送ってください。"
  - q: "「Live View は別のデバイスで開かれています」"
    a: "comma は一度に 1 台のスマートフォンかカーナビにだけ配信します。スマートフォンの CommaView でホームに戻ると、ボックスで Live View が自動で始まります。"
  - q: "スマートフォンの CarPlay も引き続き使えますか？"
    a: "はい。多くのボックスはスマートフォンの CarPlay や Android Auto をワイヤレスで中継し、それとボックスの Android を切り替えて使います。CommaView はボックスの Android モードで動きます。"
  - q: "ボックスに SIM カードは必要ですか？"
    a: "Live View には不要です。Beta の間、CommaView はアクセスパスの更新のためにときどきインターネットが必要ですが、自宅の Wi‑Fi、スマートフォンのテザリング、ボックスの SIM のどれでも構いません。"
related: [car-screens, browser-view, another-phone, connect-in-the-car]
blogPost: android-ai-box-commaview
---

## 4 種類の「CarPlay アダプター」

店では、まったく異なる 4 つのものが同じ名前で売られています。CommaView が動くのは 1 つだけです。

| 種類 | できること | CommaView が動くか |
| --- | --- | --- |
| **Android AI ボックス** | 車の画面で完全な Android が動き、スマートフォンと同じようにアプリをインストールできる | **動く** |
| **閉じた「動画」ボックス** | ロックされたシステムに、いくつかの動画配信アプリが組み込まれている | 動かない |
| **ワイヤレスアダプター** | 有線の CarPlay や Android Auto をワイヤレスにする。独自の Android はない | 動かない |
| **ポータブル CarPlay 画面** | スマートフォンの CarPlay 用の別画面。中身が Android でないことが多い | 動かない |

[CommaView に最適な Android AI ボックス](/ja/blog/android-ai-box-commaview)で、買う価値のあるボックスを比較しています。Tesla には CarPlay も Android Auto もないので、代わりに [Browser View](/ja/guides/browser-view) を使ってください。

comma のランタイムをアップデートするときは、comma を見るほかのデバイスと同じように、先にボックスの CommaView をアップデートしてください。

## 安全のために

ボックスの設定は停車中に行い、その後は触らないでください。運転中に CommaView を操作しないでください。openpilot が求めるとおり、目は道路に、手はハンドルに。comma 自身のアラートと車の計器が最優先です。CommaView は comma が見ているものを表示するだけです。
