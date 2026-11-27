---
title: "Live View で comma を見る"
description: "Live View を開いて、comma の道路カメラと走行画面をスマートフォンで見ます。操作ボタン、詳細、問題があるときの表示について。"
topic: screens
order: 1
kind: walkthrough
lede: "**Live View** は、comma の道路カメラをライブで、走行画面（comma four、comma 3X、または CommaView 独自のもの）を重ねて表示します。映像はインターネットではなく、あなた自身のネットワークを通って comma から直接届きます。"
parked: true
updated: 2026-11-27
needs:
  - title: "CommaView のセットアップ済み"
    text: "Android スマートフォンの CommaView が comma とペアリング済みであること。まだの場合は [CommaView をセットアップ](/ja/guides/setup)してください。"
  - title: "車の電源が入っている"
    text: "openpilot は走行中にだけ映像を送ります。車の電源が切れていると Live View は待機し、車が始動すると自動で始まります。"
  - title: "1 つのネットワーク"
    text: "スマートフォンと comma が同じ Wi‑Fi かテザリングにつながっていること。車内では[車内で接続する](/ja/guides/connect-in-the-car)をご覧ください。"
steps:
  - id: open
    title: "ホームから Live View を開く"
    body: |
      **ホーム** で、comma が接続済みで車の電源が入っている状態で **Live View を開く** をタップします。数秒以内に道路が表示され、配信状態のピルに **ライブ** と表示されます。
    screen: phone-home
    pins:
      - target: open-live-view
        text: "ホームのメインボタン、**Live View を開く**。"
    note: "車の電源が切れていると、Live View に **comma はオンラインですが、走行していません** と表示されます。車が始動すると自動で始まり、**更新** ですぐに始めることもできます。"
  - id: controls
    title: "映像の下の操作ボタンを覚える"
    body: |
      縦向きでは、操作ボタンは映像の下に並びます。

      - **録画** は、ドライブのこの区間を保存します。[ドライブを録画する](/ja/guides/record)をご覧ください。
      - **保存** は、ドライブの直前 3 分と次の 1 分を残します。
      - 走行画面の切り替えボタンは、表示中の画面の名前（**CommaView**、**comma 4**、**comma 3X**）が付いていて、タップするたびに次の画面に切り替わります。[走行画面を選ぶ](/ja/guides/overlays)をご覧ください。
      - **配信を開始** は、設定済みなら Live View に表示される内容を配信します。[ライブ配信する](/ja/guides/go-live)をご覧ください。
      - **ドライバーカメラ** は、映像の隅にドライバーカメラを表示します。
      - **詳細** は、Live View の情報とカードを開きます。

      スマートフォンの幅と文字サイズで収まらないものは **その他** に入ります。縮小されたり切れたりするものはありません。
    screen: phone-live-view
    pins:
      - target: record-button
        text: "**録画**。"
      - target: onroad-screen-button
        text: "走行画面の切り替え。"
      - target: driver-cam-button
        text: "**ドライバーカメラ**。"
      - target: go-live-button
        text: "ライブ配信を設定済みなら **配信を開始**。"
      - text: "**その他** には収まらないものが入ります。"
    note: "録画中は、走行画面の切り替えと **ドライバーカメラ** が淡色表示になります。**録画** をタップする前に選んでおいてください。"
  - id: details
    title: "詳細を開く"
    body: |
      **詳細** をタップするか、画面下端のシートを引き上げます。配信の状態、映像、ランタイム、comma のソフトウェアとアドレス、録画中か配信中か、そして **Browser View** カードが表示されます。リンクから **録画** と comma の **デバイス設定** を開けます。
    screen: phone-live-view-details
    pins:
      - target: details
        text: "**詳細** のシート。"
      - text: "概要：配信状態、映像、ランタイム。"
      - target: recordings-link
        text: "**録画**。"
      - target: device-settings-link
        text: "この comma の **デバイス設定**。"
  - id: turn
    title: "スマートフォンを横にする、または大きな画面を使う"
    body: |
      スマートフォンを横にすると映像が画面全体に広がり、操作ボタンは運転席側のレールに並びます。**詳細** は映像の横に開き、**終了** で Live View を離れます。
    tabs:
      - label: "横向きのスマートフォン"
        body: "レールには同じ操作ボタンが並びます。縦の短い画面ではコンパクトになります。"
        screen: phone-live-view-landscape
        pins:
          - target: record-button
            text: "レールの上端の **録画**。"
          - target: more
            text: "**その他** に **ドライバーカメラ** と **詳細** が入ります。"
          - target: exit
            text: "**終了** で Live View を離れます。"
      - label: "タブレットや車の画面"
        body: "横長の画面では、レールは運転席側にとどまります。[車の画面で CommaView を使う](/ja/guides/car-screens)をご覧ください。"
        screen: car-live-view
        pins:
          - target: record-button
            text: "**録画**。"
          - target: onroad-screen-button
            text: "走行画面の切り替え。"
          - target: driver-cam-button
            text: "**ドライバーカメラ**。"
          - target: details
            text: "**詳細**。"
          - target: exit
            text: "**終了**。"
  - id: auto
    title: "Live View が自動で開くようにする"
    body: |
      Live View を表示するためだけに置いたスマートフォンやカーナビでは、**設定 › 表示** を開き、**Live View を開いています** の **接続したら Live View を開く** をオンにします。車の電源が入った状態で comma が接続すると、Live View が自動で開きます。閉じると、次の機会まで閉じたままです。

      そのすぐ下の **ステータスバーを表示** をオンにすると、画面全体を使わずに、Live View の上にシステムの時計を表示します。
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**接続したら Live View を開く**。"
  - id: leave
    title: "終わったら Live View を離れる"
    body: |
      駐車したら **終了** か戻るをタップします。Live View を離れると、ライブ配信、Browser View、ライブコピーも終了します。Live View を開けるのは一度に 1 台のスマートフォンかカーナビだけなので、別の端末で開く前に、いま開いている端末で閉じてください。
check: "配信状態のピルに **ライブ** と表示され、道路が動き、詳細の配信状態が **良好** になっています。"
fixes:
  - q: "「comma はオンラインですが、走行していません」"
    a: "車の電源が切れているか、openpilot が起動していません。車が始動してから 30 秒以内に Live View が自動で戻ります。**更新** をタップしても構いません。"
  - q: "「この comma に接続できません」"
    a: "スマートフォンは comma と同じ Wi‑Fi か、comma のテザリングにつながっている必要があります。comma が応答すると Live View が再接続します。**再試行** をタップしても構いません。それでもだめなら、[CommaView が comma を見つけられない](/ja/guides/comma-not-found)をご覧ください。"
  - q: "「Live View は別のデバイスで開かれています」"
    a: "comma は一度に 1 台のスマートフォンかカーナビにだけ配信します。もう一方の CommaView でホームに戻ると、こちらで Live View が自動で始まります。"
  - q: "「車のデータが届きません」"
    a: "映像は届いていますが、車の速度、ウインカー、アラートが届いていません。comma を再起動すると直ります。"
  - q: "「映像が遅延」"
    a: "1 秒間、新しいフレームが届いていません。Live View は映像の横にそう表示し、映像が戻らなければ自動で再接続します。"
  - q: "「この comma の映像を再生できません」"
    a: "スマートフォンのどの動画デコーダーでも再生できませんでした。CommaView は試行を続けます。CommaView が調べられるよう、設定からサポートに報告を送ってください：[サポートに報告を送る](/ja/guides/support-bundle)をご覧ください。"
related: [overlays, record, browser-view, car-screens]
---

## 安全のために

Live View は停車中に開き、その後は触らないでください。運転中に CommaView を操作しないでください。openpilot が求めるとおり、目は道路に、手はハンドルに。comma 自身のアラートと車の計器が最優先です。CommaView は comma が見ているものを表示するだけです。
