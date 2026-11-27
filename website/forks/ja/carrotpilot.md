---
heading: carrotpilot
---
carrotpilot は、Hyundai、Kia、Genesis の車向けの openpilot フォークで、`i.carrotpilot.app` からインストールします。CommaView は carrotpilot に対して openpilot の画面を描き、速度、走行経路、車線、先行車を表示します。carrotpilot が自身の画面に加えるもの（ナビ、速度取締りカメラ、HUD など）はまだ描きません。

carrotpilot の自動アップデートや、Web ページの Git ツールは、comma が再起動するまで CommaView のフックを外します。アプリが再起動を求め、再起動後に Live View が戻ります。
