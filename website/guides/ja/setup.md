---
title: "CommaView をセットアップ"
description: "Android に CommaView アプリをインストールし、comma 3X または comma four を準備して、ガイド付きセットアップでランタイムのインストールと comma のペアリングを行います。"
topic: start
order: 1
kind: walkthrough
lede: "CommaView は 2 つの部分でできています。Android のスマートフォン、タブレット、カーナビで動くアプリと、comma で動く小さなランタイムです。アプリをインストールすると、アプリのガイド付きセットアップがランタイムを comma に入れ、確認し、ペアリングします。所要時間は数分で、P レンジに入れて openpilot を解除した状態で行います。"
parked: true
updated: 2026-11-27
needs:
  - title: "comma 3X または comma four"
    text: "openpilot または[対応フォーク](/ja/guides/forks)で動いていること。comma 3 には対応していません。comma 3 の openpilot リリースは上流で更新が止まっており、画面の描き方も異なるため、CommaView はオーバーレイを表示できません。[comma 3 に対応していない理由](/ja/#faq-comma-3)。"
  - title: "Android デバイスと招待"
    text: "Android 8 以降と、招待が届いたメールアドレス。CommaView は Beta 版のため、招待されたアカウントでログインします。"
  - title: "同じネットワーク"
    text: "スマートフォンと comma が同じローカルネットワークにあること。自宅の Wi‑Fi、スマートフォンのテザリング、comma 自身のテザリングなど、両方が参加できるものなら何でも構いません。車内の場合は[自宅の Wi‑Fi なしで接続する](/ja/guides/connect-in-the-car)をご覧ください。"
  - title: "GitHub アカウント"
    text: "comma は、入力された GitHub ユーザー名の SSH 鍵を受け入れます。鍵は CommaView が作成し、セットアップ中にあなたが GitHub に追加します。"
howItWorks:
  - title: "スマートフォン"
    text: "SSH 鍵を作成します。この鍵を GitHub に追加します。"
    edge: "SSH"
  - title: "comma"
    text: "GitHub ユーザー名から鍵を取得します。CommaView はフォークの横にランタイムをインストールします。"
    edge: "ローカルネットワーク"
  - title: "CommaView"
    text: "ランタイムの応答を確認し、comma を保存します。以後は自動で再接続します。"
steps:
  - id: get-the-app
    title: "アプリを入手してログイン"
    body: |
      Android デバイスで、招待が届いたメールアドレスを使って [my.commaview.com](https://my.commaview.com) にログインします。**Get the app** の下にある **Download CommaView** をタップします。ファイルを確認したい場合は、横に SHA-256 チェックサムが表示されています。

      ダウンロードしたファイルを開きます。Android がブラウザからのインストールを許可するよう求めるので、このインストールのために許可し、終わったら元に戻してください。

      CommaView を開きます。最初に一度だけ **CommaView の改善に協力** するかどうか（**送信** または **送信しない**）を尋ねます。次にログインを求められるので、**ログイン** をタップし、招待が届いたメールアドレスを使います。その後は、アクセスパスが有効な間はオフラインでも動作します。
    tabs:
      - label: "CommaView の改善に協力"
        body: "クラッシュレポートと、comma が動かしている運転支援ソフトウェアの種類です。映像、ドライブ、場所、名前は送りません。設定 › **プライバシーと共有** でいつでも変更できます。"
        screen: improve-commaview
        pins:
          - target: send
            text: "**送信**：問題の修正に役立つクラッシュレポートを送ります。"
          - target: dont-send
            text: "**送信しない**：スマートフォンの中に残します。"
      - label: "ログイン"
        body: "Beta の間、CommaView には招待されたアカウントが必要です。**ログイン** でブラウザが開きます。"
        screen: sign-in
        pins:
          - target: sign-in
            text: "招待が届いたメールアドレスで **ログイン**。"
    note: "カーナビや車の画面の AI ボックスにインストールしますか？ そのネットワークと comma とのペアリングは[車の画面](/ja/guides/car-screens)で説明しています。"
  - id: connect
    title: "comma のセットアップを始める"
    body: |
      注意事項を読み、非公式のソフトウェアであることと安全な使用は自分の責任であることを理解したらチェックを入れ、**理解しました — 続行** をタップします。

      **comma を接続** で **comma に CommaView をセットアップ** をタップします。
    screen: onboarding-connect
    pins:
      - target: set-up-on-comma
        text: "**comma に CommaView をセットアップ**：まだ CommaView が動いていない comma の場合。"
      - target: pair-runs
        text: "別のスマートフォンからすでに CommaView を入れている場合は、代わりに **CommaView を実行している comma をペアリング**：[別のスマートフォンやタブレットを追加](/ja/guides/another-phone)。"
  - id: setup-path
    title: "セットアップ方法を選ぶ"
    tabs:
      - label: "ガイド付きセットアップ"
        body: "**ガイド付きセットアップ**（**おすすめ** の表示があります）を選び、**ガイド付きセットアップへ進む** をタップします。CommaView が SSH 鍵を作成し、接続を案内し、comma を確認します。以降のステップはこの流れに沿っています。"
        screen: setup-choose-method
        pins:
          - target: guided
            text: "**ガイド付きセットアップ**。**おすすめ** の表示があります。"
          - target: continue
            text: "**ガイド付きセットアップへ進む**。"
      - label: "手動セットアップ"
        body: "パソコンから comma にユーザー `comma` として SSH 接続できる場合のみ。**手動セットアップ** を選んで **手動セットアップへ進む** をタップし、ターミナルからコマンドを実行します。インストーラーが 1 回限りのペアリングコードを表示したら **コマンドを実行しました** をタップし、comma の IP とコードを入力して **comma を追加** をタップします。各ステップは[ターミナルからの手動セットアップ](#ターミナルからの手動セットアップ)にあります。"
        screen: setup-manual-instructions
        pins:
          - text: "**タップしてコピー** でコマンドをコピーします。"
          - target: ran-command
            text: "インストーラーがペアリングコードを表示したら **コマンドを実行しました**。"
  - id: ssh-key
    title: "SSH 鍵を GitHub に追加"
    body: |
      CommaView がこのスマートフォン用の SSH 鍵を作成します。**鍵をコピーして GitHub を開く** をタップすると、公開鍵がコピーされ、GitHub の新しい SSH 鍵のページが開きます。

      GitHub で鍵を **Key** 欄に貼り付け、タイトルを付けて（CommaView が入力済みです）、**Add SSH key** で保存します。CommaView に戻って **続行** をタップします。
    screen: setup-ssh-key
    clip: setup-key
    pins:
      - target: copy-key
        text: "**鍵をコピーして GitHub を開く**。「SSH 鍵をコピーしました。GitHub を開いています…」と表示されます。"
      - target: own-key
        text: "**自分の SSH 鍵を使う**：GitHub に登録済みの鍵ペアを読み込みます。"
      - target: continue
        text: "GitHub に鍵を保存したら **続行**。"
    note: "GitHub に登録済みの鍵ペアがある場合は、代わりに **自分の SSH 鍵を使う** で読み込めます。秘密鍵はスマートフォンから出ません。"
  - id: comma-ssh
    title: "comma で SSH をオンにする"
    body: |
      comma の画面で **設定 → デバイス → SSH** を開きます。

      1. GitHub ユーザー名を入力します。
      2. comma が GitHub の鍵を取得するのを待ちます。
      3. SSH をオンにします。

      CommaView に戻って **続行** をタップします。
    screen: setup-enable-comma-ssh
    pins:
      - target: continue
        text: "SSH をオンにしたら **続行**。"
    note: "comma が鍵を取得するのは、ユーザー名を入力したときの一度だけです。鍵を追加する前にユーザー名を入力していた場合は、一度削除してから入力し直し、鍵をもう一度取得させてください。"
  - id: choose-comma
    title: "comma を選ぶ"
    body: |
      CommaView は、この Wi‑Fi ネットワーク上で CommaView がすでに動いている comma を一覧表示します。初めてセットアップする comma はたいてい表示されません。**自分の comma が表示されない** をタップして IP アドレスを入力し、**CommaView をインストール** をタップします。

      IP は comma の **設定 → ネットワーク** にあります。comma four では Wi‑Fi ボタンのネットワーク名の下、comma 3X では **詳細設定** の下です。
    screen: setup-choose-comma
    pins:
      - target: found-comma
        text: "CommaView がすでに動いている comma。このスマートフォンに保存済みのものには **このスマートフォンに保存済み** と表示されます。"
      - text: "**自分の comma が表示されない**：IP アドレスを入力します。"
      - target: install
        text: "**CommaView をインストール**。"
  - id: safe-install
    title: "安全なインストールを開始"
    body: |
      **安全なインストール** のダイアログに、インストール先の comma が表示されます。注意書きを読み、短いカウントダウンが終わったら **安全なインストールを開始** をタップします。
    tabs:
      - label: "車が P レンジに入っている"
        body: "車が P レンジに入っていて openpilot が作動していなければ、CommaView はすぐにインストールします。"
        screen: setup-safe-install
        pins:
          - target: start-safe-install
            text: "カウントダウンの後に **安全なインストールを開始**。"
      - label: "車が走行中"
        body: "comma はインストールを予約し、openpilot を解除して車が P レンジに入ってから実行します。走行が中断されることはありません。セットアップには **インストールを予約しました** と表示されます。openpilot を解除して車を P レンジに入れ、1〜2 分待ってから **セットアップを完了** をタップします。"
        screen: setup-install-queued
        pins:
          - target: finish-setup
            text: "車が P レンジに入ったら **セットアップを完了**。"
    note: "その後、CommaView は SSH で comma に接続し、どの comma かを確認して、このバージョンのアプリでテストされたランタイムをインストールします。インストールが応答することを確認し、comma をこのスマートフォンに保存します。終わるまでスマートフォンを同じネットワークにつないだままにしてください。"
    warn: "車の電源を入れたまま、P レンジにしておいてください。常時電源ハーネスがない場合、車の電源を切ると comma の電源も切れ、インストールが止まります。"
  - id: ready
    title: "CommaView の準備ができました"
    body: |
      comma にインストールしてペアリングが済みました。次に comma が起動すると自動で再接続します。
    tabs:
      - label: "CommaView の準備ができました"
        body: "**完了** をタップします。"
        screen: setup-done
        pins:
          - target: finish
            text: "**完了** でホームに移動します。"
      - label: "再起動してセットアップを完了"
        body: "セットアップに **再起動してセットアップを完了** と表示されることがあります。comma を一度再起動すると、スマートフォンへの配信が始まります。車の電源を切るか、openpilot を解除して P レンジに入れた状態で **comma を再起動して完了** をタップします。再起動中の約 1 分間、openpilot は停止します。"
        screen: setup-restart-to-finish
        pins:
          - target: restart
            text: "**comma を再起動して完了**。"
check: "ホームに車が表示され、comma が **接続済み** で、ランタイムと comma のアドレスが表示されます。**Live View を開く** をタップすると道路がライブで再生され、走行経路と先行車が重ねて描かれます。以後、スマートフォンと comma が同じネットワークにあれば、アドレスが変わってもアプリが自動で comma を見つけます。"
fixes:
  - q: "SSH で接続できませんでした"
    a: "comma の **設定 → デバイス → SSH** で SSH がオンになっていること、GitHub ユーザー名が自分のものであること、CommaView の鍵がその GitHub アカウントにあることを確認してください。ユーザー名を入力した後に鍵を追加した場合は、ユーザー名を削除して入力し直し、comma に鍵を取得させてください。"
  - q: "comma が一覧に表示されない"
    a: "初回はそれが普通です。一覧には CommaView がすでに動いている comma だけが表示されます。**自分の comma が表示されない** をタップして IP アドレスを入力してください（comma の **設定 → ネットワーク**。comma four では Wi‑Fi ボタンのネットワーク名の下、comma 3X では **詳細設定** の下）。スマートフォンが comma と同じネットワークにあり、VPN を使っていないことも確認してください。"
  - q: "セットアップに「インストールを予約しました」と表示される"
    a: "comma が車の走行を検知したため、待機しています。openpilot を解除して車を P レンジに入れ、1 分ほど待ってから **セットアップを完了** をタップしてください。車の電源は入れたままにします。常時電源ハーネスがない場合、車の電源を切ると comma の電源も切れます。"
  - q: "comma が対応していないと表示される"
    a: "comma 3 ではセットアップが止まり、**comma 3X または comma four に CommaView をセットアップ** が表示されます。CommaView が画面に表示を追加できないフォークでは、セットアップがその旨を伝え、何も変更しません。[comma とフォークが対応しているか確認する](/ja/guides/forks)。"
  - q: "ペアリングコードが使えなかった"
    a: "ペアリングコードは 1 回限りで、すぐに期限が切れます。インストーラーをもう一度実行して新しいコードを取得し、表示どおりに入力したか確認してください（ハイフンは省略できます）。"
  - q: "接続済みなのに映像が出ない"
    a: "セットアップとペアリングは完了しており、問題は映像の配信です。comma の電源が入って走行可能な状態か確認し、スマートフォンを同じネットワークにつないだまま Live View を開き直してください。**この comma に接続できません** と表示される場合は、[comma が見つからない](/ja/guides/comma-not-found)をご覧ください。"
related: [forks, connect-in-the-car, another-phone, setup-troubleshooting]
---

## ターミナルからの手動セットアップ

パソコンから comma にユーザー `comma` として SSH 接続できる場合のみ。

1. CommaView で **手動セットアップ** を選び、**手動セットアップへ進む** をタップします。**ターミナルからインストール** に、このアプリのランタイム用のコマンドがコピーできる状態で表示されます（**タップしてコピー**）。現在のリリースのランタイムをインストールする、次のようなコマンドです。

   ```
   curl -fsSL https://commaview.com/commaviewd/install.sh \
     | ssh comma@COMMA_IP bash
   ```

2. comma と同じ Wi‑Fi ネットワーク上のパソコンから、`COMMA_IP` を comma の IP アドレスに置き換えて実行します（comma の **設定 → ネットワーク**。comma four では Wi‑Fi ボタンのネットワーク名の下、comma 3X では **詳細設定** の下）。パソコンがインストーラーをダウンロードし、SSH が comma 上でユーザー `comma` として実行します。
3. インストーラーが終わると、comma で CommaView が起動し、1 回限りのペアリングコードが表示されます。
4. CommaView に戻り、**コマンドを実行しました** をタップします。**comma を追加** で comma を選ぶか IP を入力し、ペアリングコードを入力して **comma を追加** をタップします。アプリがランタイムを確認し、comma を保存します。

## 初めて運転する前に

運転する前に、P レンジに入れた状態で試してください。

- ホームで comma が **接続済み** と表示されている。
- Live View が再生され、走行経路が車の動きに合わせて動く。
- アプリに警告が出たり修復を求められたりしたら、運転する前に解決する。
- 運転中に操作が必要にならないように設定しておく。

まだ解決しない場合は、[CommaView Discord](https://discord.gg/UuMhz9K8ft) で質問するか、アプリからフィードバックを送ってください。サポートからログを求められたら、[サポートバンドルを送ってください](/ja/guides/support-bundle)。
