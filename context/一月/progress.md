# Progress — current focus

> Purpose: Forward-looking snapshot — "where am I right now in this workspace?"
> Update when: focus shifts, a task completes, priorities change. OVERWRITE in place — a
>   snapshot, not a log.
> BUDGET: ~120 lines. SECTIONS FIXED (below). NO dated "Prior…" / "Earlier…" history blocks —
>   a second dated block is the signal to APPEND to journal.md and OVERWRITE this file.
> Single source: history -> journal.md, durable facts -> reference.md; here, only POINT to them.

> **路徑約定(2026-10-26 起)**:本檔內容自 東京遊/.context 套用而來。文中的 output/、input/、coord/、
>   Claude outputs/ 一律指「一月/東京遊/」底下(例:output/行程網頁_v9.html = 東京遊/output/行程網頁_v9.html);
>   完整歷史 journal 在 東京遊/.context/on-demand/journal.md。

## Now
- 行程 2027/1/8–1/16 共9天,骨架與每日時間軸全部定案;細節見 reference.md「行程決定」。
- 住宿:2026-10-26 迪士尼段改成 Vacation Package(Fantasy Chateau,1/11–1/13 住 2 晚),**1/13 晚上空缺**;其餘已訂(見 reference.md)。Package 設施/餐廳/各日園區已從 Gemini 對話取得:1/12 樂園、1/13 海洋(見 reference.md「Vacation Package 已選內容」)。
- 餐食:Day1–Day6 與 Day9 全部定案;**僅剩 Day7 午餐+晚餐、Day8 晚餐、Day9 成田晚餐未定**(使用者考慮中)。
- 行程網頁現行版 = output/行程網頁_v9.html(13 個分頁,含「待辦清單」28 項與「行程影像」31 畫面)。
- 線上版 GitHub Pages 含真實地圖/照片、手機可用;已發 v1.0 Release 標記 commit 360d794。
- 最近一次變更:2026-10-26 迪士尼段改成 Vacation Package,並從 Gemini 對話取得已選內容(見一月 journal.md 2026-10-26 續2〜續3)。行程網頁 v9 還沒反映這次變更。

## Next (1–3)
- **Day5/Day6 迪士尼排程(Package 版)**:設施與園區已知,可開始排。注意 1/12 樂園無 Happy Entry(對象外日);兩天早餐都是 06:40;Day5/6 晚餐已由 Package 包含(北齋、麥哲倫),reference.md「Day5/Day6 餐食」需改寫。
- Day7 午餐+晚餐、Day8 晚餐、Day9 成田晚餐:待使用者決定(可請 Claude 先出候選比較表)。
- 四處優先路線風險:A1 Day2 取車緩衝降級方案、A2 天上山纜車上行末班、A3 天空鳥居停車判斷點、
  A5 新橋飯店寄放行李(多數需電話/email 確認,見 todo.md 電話清單)。
- 待使用者確認:API 金鑰網域/預算警示、「近郊天數預算2天」是否改3天2夜、富士回遊與租車是否訂妥、BR198 時刻。

## Blockers
- (無 Pages blocker:2026-10-17 查得最新 build 狀態 built,對應 main 最新 commit e7aeaa6)
- 第四輪派工待預檢:5 小時用量剩餘需 ≥40%、worker session 需使用者手動開
  (見 output/multi-work/東京遊_plan_v1.md §0)。

## Pointers
- 歷史紀錄 -> 東京遊/.context/on-demand/journal.md(2026-08-17 ~ 2026-10-17);2026-10-26 起 -> 一月/.context/on-demand/journal.md
- coord/ -> 第一〜三輪協調區(已封存;retro 見 coord/retro_v1.md)
- output/multi-work/東京遊_plan_v1.md -> 第四輪分工計畫(T17–T19 已備妥);prompts 見 _prompts_v1.md
- output/行程網頁_v9.html + output/行程表_v1.xlsx(分頁「2027 Jan」) -> 現行行程最新版
  (xlsx 尚未同步 2026-10-06 的餐食決定)
- 行程網頁手機完整版(含地圖/照片) -> https://ErickLCloud.github.io/Ericktrip/
  (repo ErickLCloud/Ericktrip;更新流程與 gh CLI 設定見 reference.md)
- v1.0 Release -> https://github.com/ErickLCloud/Ericktrip/releases/tag/v1.0
- 行程網頁輕量線上版(無地圖/照片,仍停在 v2) -> https://claude.ai/code/artifact/bbbfe1b7-e685-4079-b687-9d46e7fff2e4
- output/河口湖景點清單_v4.md + 河口湖景點勾選工具_v1.html -> https://claude.ai/code/artifact/908c3994-3193-4418-9fb2-e5c5f8b44665
- output/鎌倉景點清單_v1.md + 鎌倉景點勾選工具_v1.html -> https://claude.ai/code/artifact/ec5bf9ad-336d-4b78-bf41-997e98132eff
- output/東京美食候選地圖_v1.html -> https://claude.ai/code/artifact/7bd0b757-65e2-434f-bd2a-9506eca9cf7b
- output/景點清單_v1.md, output/東京景點地圖_v1.html -> 東京景點清單
- output/行程規劃_v1.md -> 已作廢,不再引用
