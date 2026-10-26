# Reference (stable facts) — the durable-facts sink

> Purpose: Durable technical/contextual facts and locked decisions that rarely change. This is
>   the HOME for durable facts — so progress.md can stay ephemeral.
> Update when: a stable fact changes, or a decision locks (rare). Not a log.
> Focus: things expensive to re-derive — environment, key file locations, conventions, specs,
>   locked architecture, pointers to the latest deliverable versions.
> FORMAT (for retrieval): prefer one fact/decision per line with a stable ID + status, so a cold
>   session can GREP instead of reading the whole file, e.g.  `D3 | output dir = OUT/<branch> | LOCKED`.
> BUDGET: ~250 lines, read at session start. When it grows past that, SPLIT the cold parts to
>   on-demand/reference-archive.md and leave a one-line pointer here.

## 鎖定事實（LOCKED）
- R1 | 旅遊日期 = 2027/1/8（五）～1/16（六），共9天8夜 | LOCKED
- R2 | 去程 BR198 桃園(TPE)→成田(NRT) 參考08:50/12:55；回程 BR195 成田(NRT)→桃園(TPE) 參考20:20/23:25（冬季班表，實際以電子機票為準） | LOCKED
- R3 | 進出機場為成田(NRT)，非羽田 | LOCKED
- R4 | 同行2人（情侶/夫妻），興趣：美食/購物/文化歷史/近郊小旅行，近郊天數預算2天(可含1泊) | LOCKED
- R5 | Day5(1/12二)、Day6(1/13三) = 東京迪士尼樂園/海洋 | LOCKED
- R6 | Day1–4、Day7–9 尚未決定 | OPEN
- R7 | 河口湖交通方式已定案：新宿↔河口湖駅搭電車(JR特急富士回遊,約1h53,¥4,200)或高速巴士(バスタ新宿,約1h40,¥2,200)，抵達河口湖駅後才當地租車自駕，2天1夜，不開高速公路、不在東京市區租車 | LOCKED
- R7b | 迪士尼2天與河口湖2天1夜的先後順序 尚未決定 | OPEN
- R8 | 使用者已明確表示行程不由 Claude 主動排逐日流程，僅在使用者要求特定模組時產出 | LOCKED

## 產出物索引
- output/東京迪士尼與河口湖自駕行程_2027年1月版_v2.html — 【目前採用版本】迪士尼2天+河口湖2天1夜(電車進河口湖+當地租車自駕)景點清單/地圖/交通計畫，格式比照 input/伊豆半島10日自駕行程_2027年1月版.html，每景點附Google Map連結
- output/東京迪士尼與河口湖自駕行程_2027年1月版_v1.html — 舊版，河口湖為「新宿全程自駕」方案A(1日)/方案B(1泊2日)，已被v2取代，保留供比較
- 靜岡富士山景點清單_v1.md、富士山景點比較_v1.html — 河口湖 vs 靜岡側富士山景點研究（舊「東京遊」專案帶過來的產出）
- input/日本遊一月_session摘要.md、input/日本遊一月_session交接_2026-08-23.md — 舊「東京遊」專案的完整交接記錄（迪士尼快速通關/飯店比較、河口湖景點清單v3含查證狀態、靜岡富士山景點清單v1、伊豆半島格式規格分析），已拆解重點進本檔與journal.md，原始交接檔保留在 input/ 供查對

## 格式規格（伊豆半島樣式，本專案輸出物比照）
- 單一自包含 HTML(inline CSS+JS)，分頁式（tab切換，非線性長頁），可用左右鍵/上下頁按鈕切換，history hash 記錄目前分頁
- CSS變數色票（--sea藍/--plum洋紅/--sun橘/--leaf綠/--ink墨），Noto Sans TC字體，卡片式圓角陰影
- 每日/每模組頁：badges標籤 → 景點照片卡(pgrid, 連結Wikimedia Commons，找不到圖時灰色斜紋fallback) → 手繪風格SVG路線圖(含比例尺/指北針/圖例) → 時間軸清單(.tl) → note/warn/tip三色提示框 → 住宿建議框(.stay)
- SVG地圖：範本(伊豆半島)是依實際經緯度轉換的精確海岸線路徑，工程量很大；本專案河口湖/迪士尼版改用「示意配置圖」簡化畫法(相對位置正確但非精確經緯度)，圖說已誠實標註「示意圖，非精確經緯度」
- 照片：僅少數已核實存在的 Wikimedia Commons 檔案才放真實 img+連結，其餘一律用 .noimg 灰色色塊卡呈現重點說明，不編造圖檔連結
