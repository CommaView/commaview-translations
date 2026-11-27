---
title: "タブレットや車の画面で CommaView を使う"
description: "CommaView の Live View を大きな画面で：Android カーナビ、車の画面につなぐ Android AI ボックス、マウントしたタブレット。インストール、ネットワーク、ペアリング、レイアウト。"
topic: screens
order: 3
kind: walkthrough
lede: "comma 3X と comma four の画面は小さめです。CommaView は comma の Live View を、Android カーナビ、車の画面につなぐ Android AI ボックス、マウントしたスマートフォンやタブレットといった大きな画面に表示します。車の画面では CommaView が個別に動き、comma とペアリングします。"
parked: true
updated: 2026-11-27
needs:
  - title: "Android 8 以降"
    text: "Android 8 以降で動き、アプリをインストールできるカーナビ、AI ボックス、スマートフォン、タブレット。"
  - title: "招待"
    text: "CommaView の招待が届いたメールアドレス。my.commaview.com とアプリへのログインに使います。"
  - title: "スマートフォンの CommaView"
    text: "いちばん簡単なのは、先にスマートフォンから comma をセットアップし、その後で車の画面をペアリングする方法です。[CommaView をセットアップ](/ja/guides/setup)。"
howItWorks:
  - title: "comma"
    text: "インターネットではなく、ローカルネットワークで Live View を送ります。"
    edge: "テザリングまたは Wi‑Fi"
  - title: "車の画面"
    text: "個別の CommaView が動き、comma とペアリングします。"
steps:
  - id: install
    title: "車の画面に CommaView をインストールする"
    body: |
      カーナビ、AI ボックス、スマートフォン、タブレットの Web ブラウザを開き、招待が届いたメールアドレスで [my.commaview.com](https://my.commaview.com) にログインします。**Get the app** の下の **Download CommaView** をタップし、ダウンロードしたファイルを開いて、このインストールのためにブラウザからのインストールを許可し、終わったら元に戻します。[セットアップガイド](/ja/guides/setup)と同じ手順です。

      CommaView を開いてログインします。Beta の間はアクセスパスの更新のためにときどきインターネットが必要なので、少なくともたまにはインターネットにつながる Wi‑Fi に接続してください。
    note: "カーナビやボックスによっては、ブラウザからのインストールがブロックされます。パソコンでアプリをダウンロードし、USB メモリーでコピーして、本体のファイルマネージャーから開いてください。"
  - id: network
    title: "comma と同じネットワークにつなぐ"
    body: |
      Live View はローカルネットワークを通って comma から車の画面に直接届きます。同じネットワークにあればよく、車内ではたいていテザリングを使います。車の始動と同時に自動で立ち上がるものを選ぶのが、たいてい一番手間がかかりません。
    tabs:
      - label: "車の画面のテザリング"
        body: "AI ボックスやカーナビがテザリングを共有できる場合（SIM カード付きのものの多くは可能です）、オンにして、comma の **設定 › ネットワーク** で comma を参加させます。"
      - label: "スマートフォンのテザリング"
        body: "comma と車の画面をスマートフォンのテザリングに参加させます。どちらもそこからインターネットを使えます。"
      - label: "comma のテザリング"
        body: "comma のテザリングをオンにして（comma four では **設定 › ネットワーク › テザリングを有効化**、comma 3X では **設定 › ネットワーク › 詳細設定 › テザリングを有効化**）、車の画面から参加します。"
      - label: "自宅の Wi‑Fi"
        body: "自宅では、両方を自宅の Wi‑Fi に接続します。セットアップには便利ですが、車で出かけると切れます。"
    note: "車の画面の VPN はオフにしてください。テザリングによっては接続したデバイス同士を隔離するものがあります。あるテザリングで車の画面が comma を見つけられない場合は、別のものを試してください。詳しくは[車内で接続する](/ja/guides/connect-in-the-car)をご覧ください。"
  - id: pair
    title: "comma とペアリングする"
    body: |
      スマートフォンからすでに comma に CommaView を入れている場合は、セットアップし直すのではなく、車の画面をペアリングします。車の画面は専用の鍵を受け取ります。
    tabs:
      - label: "スマートフォンで"
        body: |
          comma の **デバイス設定** を開き、**別のスマートフォンをペアリング** を開きます。**別のスマートフォンを追加** の下の **招待を表示** をタップします。入力するコードか QR コードが表示され、10 分間有効で 1 回だけ使えます。
        screen: device-pairing
        pins:
          - target: show-invitation
            text: "**招待を表示**。"
          - target: this-phone
            text: "鍵を持つスマートフォン。このスマートフォンには **このスマートフォン** と表示されます。車の画面もここに加わります。"
      - label: "車の画面で"
        body: |
          **comma を接続** で **CommaView を実行している comma をペアリング** をタップします（すでに comma を追加している場合は、代わりに **comma を追加** を開きます）。comma を選んで **ペアリングコードを入力** か **QR コードをスキャン** をタップします。表示されない場合は **アドレスとコードを入力** をタップします。**ペアリングコードまたは招待** に招待を入力し、**comma をペアリング** をタップします。
        screen: add-comma
        pins:
          - target: found-comma
            text: "このネットワーク上で見つかった comma。"
          - target: scan-qr
            text: "**QR コードをスキャン**。"
          - target: enter-address
            text: "表示されない場合は **アドレスとコードを入力**。"
    note: "その後、スマートフォンに **新しいスマートフォンが鍵を取得しました** と表示されます。**自分のものです** をタップします。すべての手順は[別のスマートフォンやタブレットを追加する](/ja/guides/another-phone)にあります。"
  - id: fit
    title: "画面に合わせる"
    body: |
      横長の画面では、CommaView はダッシュボードとしてレイアウトされ、ナビゲーションは横のレールに入ります。本体の文字サイズは、ひと目で読める大きさにしておいてください。CommaView はそのサイズで使える広さに合わせてレイアウトします。

      Live View の操作ボタンは運転席側に並びます。**自動** では comma が報告する側に従います。自分で設定するには **設定 › 表示 › 運転席の位置** で **自動**、**左ハンドル**、**右ハンドル** から選びます。すべての画面で操作ボタンが左右反転します。
    tabs:
      - label: "タブレット"
        body: "ホームには、車、今週の記録、地図、ドライブが並んで表示され、横にレールがあります。"
        screen: tablet-home
        pins:
          - target: home-tab
            text: "レール：**ホーム**、**録画**、**設定**。"
          - target: open-live-view
            text: "**Live View を開く**。"
      - label: "カーナビ"
        body: "同じダッシュボードを、ダッシュボード埋め込みの画面に合わせたサイズで表示します。"
        screen: car-home
        pins:
          - target: home-tab
            text: "レール：**ホーム**、**録画**、**設定**。"
          - target: open-live-view
            text: "**Live View を開く**。"
      - label: "AI ボックス経由"
        body: |
          車によっては、AI ボックスが送る映像の端を切り取ってしまい、Android はそれを検知できません。**設定 › 表示 › 画面の端** を開き、線が一周すべて見えるまで各辺を内側に動かします。その後、ホーム、Live View、設定が内側に収まっているか確認します。そこにある **テーマ** は車の画面に合わせられます：**この端末と同じ**。
        screen: settings-screen-edges
        pins:
          - target: done
            text: "**−** と **+** で各辺を内側に動かし、**完了** で保存します。"
  - id: live-view
    title: "Live View を開いて再生を確認する"
    body: |
      車の電源を入れた状態で **Live View を開く** をタップします。操作ボタンは道路の横、運転席側のレールに並び、縦の短い画面ではコンパクトになります。
    tabs:
      - label: "タブレット"
        body: "**詳細** は映像の横のペインに開きます。"
        screen: tablet-live-view
        pins:
          - target: details-pane
            text: "映像の横の詳細。"
          - target: record-button
            text: "**録画**。"
          - target: go-live-button
            text: "**配信を開始**。"
      - label: "カーナビ"
        body: "レールには、録画、走行画面の切り替え、ドライバーカメラ、詳細、終了が並びます。"
        screen: car-live-view
        pins:
          - target: record-button
            text: "**録画**。"
          - target: onroad-screen-button
            text: "走行画面の切り替え。"
          - target: driver-cam-button
            text: "**ドライバーカメラ**。"
          - target: details
            text: "ドライバーカメラの下の **詳細**。"
          - target: exit
            text: "**終了**。"
  - id: auto
    title: "自動で開くようにする"
    body: |
      **設定 › 表示** の **Live View を開いています** で：

      - **接続したら Live View を開く**：車の電源が入った状態で comma が接続すると、自動で Live View を開きます。
      - **このデバイスの起動時に CommaView を開く**：車と一緒に再起動するカーナビ向けです。再起動せずスリープするものには、起動するアプリの一覧が別にある場合があります。
      - **Bluetooth 接続時に自動で開く**：選んだデバイス（車、カーナビならスマートフォン）が接続したときに開きます。

      **他のアプリの上に重ねて表示** が許可されていれば、CommaView は自動で開きます。許可されていない場合は、開くかどうかを通知で尋ねます。
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**接続したら Live View を開く**。"
check: "車の電源を入れると車の画面で Live View が開き、配信状態のピルに **ライブ** と表示され、すべての操作ボタンが画面の端の内側にあります。"
fixes:
  - q: "CarPlay や Android Auto で CommaView を使えますか？"
    a: "スマートフォンからは使えません。CommaView は CarPlay や Android Auto のアプリではなく、これらのプラットフォームは走行中にスマートフォンのアプリが映像を表示することを許可していません。Android AI ボックスならこれを回避できます。ボックス自体が Android デバイスなので、CommaView はボックス上で動き、車はボックスの画面を表示します。[Android AI ボックスで CommaView を使う](/ja/guides/ai-box)をご覧ください。"
  - q: "車に内蔵の Android Automotive（Google 搭載）で使えますか？"
    a: "まだ使えません。Google 搭載の車は専用の Play ストアからしかアプリをインストールできず、そこに CommaView はありません。別の方法で試した場合は、結果を教えてください。"
  - q: "同じ comma で車の画面とスマートフォンの両方を使えますか？"
    a: "はい。それぞれを comma とペアリングしてください。Live View を使えるのは一度に一方だけなので、先にもう一方の Live View を閉じます。Live View に **Live View は別のデバイスで開かれています** と表示され、もう一方でホームに戻ると自動で始まります。"
  - q: "車が映像の端を切り取ってしまう"
    a: "車によっては AI ボックスが送る映像を切り取ってしまい、Android はそれを検知できません。**設定 › 表示 › 画面の端** で設定した各辺から、アプリの表示を離します。"
  - q: "車の画面が comma を見つけられない"
    a: "CommaView は同じネットワーク上で、アドレスが変わっても自動で comma を見つけます。見つからない場合は comma の IP アドレスを入力してください。comma 自身のテザリングでは 192.168.43.1（どの comma でも同じ）、それ以外のネットワークでは comma の **設定 › ネットワーク** に表示される IP アドレスです。comma four では Wi‑Fi ボタンのネットワーク名の下、comma 3X では **詳細設定** の下にあります。"
  - q: "ランタイムのアップデート後、車の画面に映像が届かなくなった"
    a: "comma のランタイムをアップデートするときは、先に、その comma を見るすべてのデバイス（車の画面も含む）で CommaView をアップデートしてください。古い CommaView の車の画面は、comma の最初のスマートフォンが鍵を受け取ってから 90 日間は使えます。それ以降は CommaView 0.0.166 以降と招待が必要です。"
related: [ai-box, browser-view, another-phone, connect-in-the-car]
---

## 運転中に使えるもの

CommaView は Android アプリなので、目の前に Android デバイスが必要です。次のどれでも、運転中に CommaView を動かせます。

- **Android カーナビ。** Android 8 以降で動く社外品のカーナビ。スマートフォンと同じように CommaView をインストールでき、運転中も車の画面で動きます。
- **Android の「AI ボックス」。** 車の有線 CarPlay や Android Auto のポートに差し込み、そこに自身の Android 画面を表示する小型の Android コンピューター。CommaView はスマートフォンではなくボックス上で動きます。[Android AI ボックスで CommaView を使う](/ja/guides/ai-box)をご覧ください。
- **マウントしたスマートフォンやタブレット。** 視界を妨げないダッシュボードやエアコン吹き出し口のマウントに付けた、Android のスマートフォンやタブレット。最も簡単で、多くの人が使っている方法です。

Tesla のように Web ブラウザを持つ車では、代わりにそのブラウザに Live View を表示できます：[車のブラウザに Live View を表示する](/ja/guides/browser-view)。

## 使えないものとその理由

- **スマートフォンからの CarPlay と Android Auto。** CommaView は CarPlay や Android Auto のアプリではありません。これらのプラットフォームは、走行中にスマートフォンのアプリが映像を表示することを許可していません。
- **CarPlay と Android Auto での停車中の動画。** Apple と Google は一部の車で動画に対応しつつありますが、停車中だけなので、走行中に Live View は表示できません。
- **スマートフォンの画面を車にミラーリングする方法。** CarPlay や Android Auto 経由でスマートフォンの画面をミラーリングするアダプターには対応していません。代わりに、CommaView 自体が動く Android AI ボックスかカーナビを使ってください。
- **Google 搭載（Android Automotive）。** これらの車は専用の Play ストアからしかアプリをインストールできず、そこに CommaView はありません。

## テスト済みのハードウェア

CommaView チームが実際に走行して使った車の画面です。CommaView は Android 8 以降のデバイスならどれでも動くはずですが、確認済みなのは次のものです。

| デバイス | 種類 | 確認した内容 |
| --- | --- | --- |
| **Doro head unit**（Qualcomm QCM6125、Android 13、1280 × 720） | カーナビ | 市街地走行での Live View（2026 年 10 月）。 |
| **Dasaita 10.2″ head unit**（1280 × 720、Toyota RAV4 に搭載） | カーナビ | 走行中の Live View、停車中の録画のアップロード。 |

**テストにご協力ください。** 車の画面はそれぞれ異なります。カーナビやボックスで CommaView を使っている場合は、[結果を教えてください](#車の画面について教えてください)。確認できたらここに追加します。

## 車の画面について教えてください

報告に機種と画面サイズが含まれるよう、車の画面そのものから送ってください。

1. カーナビやボックスの CommaView で **設定 › サポートと診断** を開き、**問題を報告、またはアイデアを送る** をタップします。
2. **アイデア** を選び、**この端末の診断データ** をオンにします（アイデアではオフになっています）。メーカー、機種、画面サイズがわかります。
3. メモに、車、カーナビやボックス（ブランドと機種）、接続方法（誰のテザリングか、または Wi‑Fi）、うまくいったこととうまくいかなかったことを書いて、**送信** をタップします。

送った内容と返信は、[my.commaview.com](https://my.commaview.com/feedback) の Your feedback で確認できます。まだ Beta に参加していない、またはアプリが起動しない場合は、[CommaView Discord](https://discord.gg/UuMhz9K8ft) で教えてください。

## 安全のために

- インストール、ペアリング、レイアウトの設定は停車中に行ってください。運転する前に Live View が再生されることを確認してください。
- 運転中に CommaView を操作しないでください。openpilot が求めるとおり、目は道路に、手はハンドルに。
- comma 自身のアラートと車の計器が最優先です。CommaView は comma が見ているものを表示するだけです。
- スマートフォンやタブレットは、視界やエアバッグを妨げない場所に取り付け、車内の画面に関する地域の規則に従ってください。
