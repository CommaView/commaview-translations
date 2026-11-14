# 日本語 glossary

The words every Japanese string uses for CommaView's terms, so screens translated apart say the same thing. Where
openpilot already translates a term (`selfdrive/ui/translations/app_ja.po`; its older Qt `main_ja.ts` where the .po
has none), its word is used, so the app says what the car's screen says. Machine drafted; a native speaker's review
is owed before release (the plan).

## Kept as they are

Names are never translated: **CommaView**, **comma** (the device, lower case, as comma writes it), **comma 3X**,
**comma four**, **openpilot**, **sunnypilot**, **dragonpilot**, **carrotpilot**, **StarPilot**, **BluePilot** and the
other forks, **Live View** (the feature's name, as on commaview.com), **Surround**, **Car screen**, **YouTube**,
**Twitch**, **X**, **Stadia Maps**, **OpenStreetMap**, **Buy Me a Coffee**, **GitHub**, **Discord**, **Wi‑Fi**,
**SSH**, **QR**, **Beta**, **Alpha**, units (`km/h`, `mph`, `m`, `ft`, `GB`, `MB`, `fps`).

## Style

- Polite **です／ます** style in sentences, as openpilot's translation writes. The person is rarely addressed;
  where a sentence needs it, あなたの (as openpilot's "あなたの comma アカウント"), otherwise leave it out.
- Full-width punctuation in Japanese text: 、。「」（）：？！. Quotes are 「」, nested 『』. Ellipsis stays …, as the
  English has it.
- Spacing: no space between Japanese and a number or a unit-less Latin abbreviation in running text where openpilot
  writes none ("SSH鍵", "QRコード"); a half-width space around a lower-case or multi-word Latin name so it stays
  readable ("comma の", "Live View を", "25.7 GB 空き"). None before or after full-width punctuation.
- Buttons are short: noun + する dropped where the noun reads as an action, as Android and openpilot do:
  キャンセル, 完了, 保存, 削除, 再試行, 続行, 開く, 閉じる, 有効化, 無効化.
- No trailing 。 on titles, buttons, row titles or pills; whole sentences in body text end with 。.
- Katakana loanwords follow openpilot and Android's own Japanese (アップデート, インストール, ペアリング,
  デバイス), with the long-vowel mark Android uses (ユーザー, サーバー, フォルダー).

## Terms

| English | 日本語 | Note |
|---|---|---|
| Home (dock) | ホーム | |
| Recordings | 録画 | the section and its saved drives |
| Settings | 設定 | |
| recording, a recording | 録画 | |
| drive (a trip the comma recorded) | ドライブ | |
| replay | リプレイ | |
| live copy | ライブコピー | |
| saved moment | 保存した場面 | |
| Record | 録画 | the rail's button |
| Go live / live streaming | ライブ配信 | |
| onroad screen | 走行画面 | |
| onroad / offroad (the comma's state) | 走行中 / 停車中 | |
| design (an onroad screen's look) | デザイン | |
| overlay pack | オーバーレイパック | |
| fork | フォーク | openpilot's own jargon; kept in katakana |
| runtime (commaviewd) | ランタイム | |
| update / install / uninstall | アップデート / インストール / アンインストール | openpilot's |
| reboot | 再起動 | openpilot's |
| power off | 電源オフ | openpilot's |
| pair / pairing | ペアリング | openpilot's |
| device (the comma) | デバイス | openpilot's |
| this phone / this device (the device CommaView runs on) | このスマートフォン / この端末 | openpilot says スマートフォン; `common_this_phone` / `common_this_device`, a sentence's placeholder (how-to-localize.md, "This phone or this device") |
| your phone / your device (`common_your_*`) | お使いのスマートフォン / お使いの端末 | |
| connected / disconnected | 接続済み / 切断 | |
| offline | オフライン | openpilot's |
| engaged / disengaged | 作動中 / 解除 | openpilot uses 解除 for disengaging |
| override | ドライバー介入 | |
| experimental mode | 実験モード | openpilot's |
| driver monitoring | ドライバーモニタリング | openpilot's |
| driver camera | ドライバーカメラ | openpilot's |
| road camera / wide camera | 道路カメラ / 広角カメラ | |
| lead car | 先行車 | |
| speed limit | 制限速度 | |
| set speed / MAX | 設定速度 / 最大 | openpilot's MAX is 最大 |
| lane change | 車線変更 | |
| calibration | キャリブレーション | openpilot's |
| driver position (left/right-hand drive) | 運転席の位置（左ハンドル／右ハンドル） | |
| daylight contrast | 日中コントラスト | |
| offline maps | オフライン地図 | |
| navigation | ナビ | |
| Home / Work (places) | 自宅 / 職場 | |
| vehicle location | 車両の位置 | openpilot says 車両 |
| account / sign in / sign out | アカウント / ログイン / ログアウト | openpilot says login |
| leaderboard | ランキング | |
| achievement | 実績 | |
| privacy | プライバシー | |
| diagnostics | 診断データ | |
| report a problem | 問題を報告 | |
| Details (Live View's pane) | 詳細 | |
| stream health | 配信状態 | |
| storage | ストレージ | |
| hotspot | テザリング | openpilot's word for the comma's hotspot |
| Live / Delayed (Live View's state) | ライブ / 遅延 | |
| frame pacing | フレームペーシング | |
| inset (a picture in the picture) | 小窓 | |
| framing: Fill / Exact / Extend / Auto | 全画面 / 正確 / 拡張 / 自動 | |
| camera framing | カメラの表示範囲 | |
| reduce motion | 動きを減らす | |
| screen edges | 画面の端 | |
| View (Surround's) / chase / high / top-down | 視点 / 追従 / 高所 / 真上 | |
| vehicle detection / detector / model | 車両検出 / 検出器 / 検出モデル | |
| renderer | レンダラー | |
| key (an API key, an SSH key) | 鍵 / キー | SSH鍵 (openpilot's); API キー; public / private: 公開鍵 / 秘密鍵 |
| dashboard (a service's) | ダッシュボード | |
| reroute | ルート再検索 | |
| Where to? | どこへ行きますか？ | |
| map source | 地図ソース | |
| Powered by | 提供 | |
| steering / speed active, manual (the HUD's control line) | ステアリング制御中 / 速度制御中 / 手動 | review on a drive |
| steering only / speed only | ステアリングのみ / 速度のみ | |
| blind spot | 死角 | |
| green light / lead car moving | 青信号 / 先行車発進 | |
| safe update / install / repair | 安全なアップデート / インストール / 修復 | |
| overlays (drawn on video) | オーバーレイ | not overlay packs (オーバーレイパック) |
| telemetry | テレメトリー | |
| patch | パッチ | |
| in Park | P レンジ | |
| power harness | 常時電源ハーネス | |
| guided / manual setup | ガイド付きセットアップ / 手動セットアップ | openpilot's セットアップ |
| boot hook / runtime hook | 起動フック / ランタイムフック | |
| vehicle security key | 車両セキュリティキー | |
| pair code / invitation | ペアリングコード / 招待 | |
| phones with a key | 鍵を持つスマートフォン | |
| shared token | 共有トークン | |
| development runtime | 開発版ランタイム | |
| controller | コントローラー | |
| best effort | ベストエフォート | |
| video only | 映像のみ | |
| widgets | ウィジェット | |
| backup / restore | バックアップ / 復元 | |
| read-only | 読み取り専用 | |
| head unit | カーナビ | the car's own screen |
| nearby devices | 付近のデバイス | Android's permission |
| display over other apps | 他のアプリの上に重ねて表示 | Android's permission |
| set aside (saved lists) | 取り置き | |
| Not now / Review | 後で / 確認 | openpilot's REVIEW is 確認 |
| queue | キュー | |
| Needs processing | 処理待ち | |
| pull drives | ドライブを取得 | |
| whole drive | ドライブ全体 | |
| export | 書き出し | |
| pack studio | パックスタジオ | |
| clip | クリップ | |
| log excerpt | ログの抜粋 | |
| support bundle | サポートバンドル | |
| Driving insights | 運転の記録 | |
| contribute | 協力 | openpilot: 改善に協力 |
| route / segment (openpilot's) | ルート / セグメント | |
| Privacy & sharing | プライバシーと共有 | the Settings page |
| stream key | ストリームキー | YouTube's |
| destination (Go live's) | 配信先 | |
| Go live | 配信を開始 | |
| YouTube Studio | YouTube Studio | YouTube's own name in Japanese |
| Auto-start | 自動開始 | |
| Public / Unlisted / Private | 公開 / 限定公開 / 非公開 | YouTube's |
| input (microphone) | 入力 | |
| car hands-free | 車のハンズフリー | |
| metered / monthly limit | 従量課金 / 月間上限 | openpilot's 従量課金 |
| Your requests | あなたのリクエスト | |
| Open / Closed (a request) | 対応中 / 完了 | |
| license | ライセンス | |
| map library | 地図ライブラリ | |
| map theme | 地図のテーマ | |
| spoken guidance | 音声案内 | |
| dev build | 開発版 | |
| access pass | アクセスパス | the account's |
| waitlist | 順番待ちリスト | |
| beta member / admin | Beta メンバー / 管理者 | |
| display name / public name | 表示名 / 公開名 | the leaderboard's |
| This week / Last week / Lifetime (the board's periods) | 今週 / 先週 / 累計 | |
| finalized (a week) | 確定 | |
| badge / share card | バッジ / シェアカード | |
| Official / Community (packs) | 公式 / コミュニティ | |
| reviewed by CommaView / unreviewed | CommaView 審査済み / 未審査 | |
| Update ready | アップデート可能 | |
| training collection | 学習データ集 | car detection's; openpilot's 学習データ |
| recording metadata | 録画のメタデータ | |
| SSH identity (a comma's host key) | SSH ID | |
| keystore | キーストア | Android's |
| repository (a fork's) | リポジトリ | |
| driving software | 運転支援ソフトウェア | openpilot or a fork, as a message names it |
| put back the way it was (rolled back) | 元の状態に戻す | |
