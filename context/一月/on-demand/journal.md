# Journal — history

> Purpose: Backward-looking record — "what happened and why".
> Update when: after significant work, a decision or a commit. APPEND only (newest at bottom).
>   Never edit past entries.
> BUDGET: none — unbounded by design.
> NOT read at session start. Read only when history or an audit is needed.

Entry format:
## YYYY-MM-DD HH:MM — <title>
- What / why / outcome (+ commit hash if any)

---

## 2026-08-23 — 專案初始化 + 迪士尼/河口湖景點清單產出
- What：① 用 project-init 骨架化「日本遊一月」資料夾（claude.md + .context + input/output）。② 讀取使用者放在 input/ 的兩份舊「東京遊」專案交接檔（session摘要.md、session交接_2026-08-23.md）與範本 input/伊豆半島10日自駕行程_2027年1月版.html。③ 依使用者需求，產出 output/東京迪士尼與河口湖自駕行程_2027年1月版_v1.html：涵蓋東京迪士尼樂園/海洋(各一天，已鎖Day5/6)景點清單+示意園區地圖+交通(電車)計畫，以及河口湖自駕景點清單+示意路線地圖+交通(自駕)計畫(方案A 1日來回 / 方案B 1泊2日兩版，因天數尚未決定)。
- Why：使用者明確要求比照伊豆半島範本格式，先做這兩個可插入9天8夜行程的模組，其餘天數(Day1–4、Day7–9)仍由使用者自行決定。
- 做法取捨：伊豆半島範本的SVG地圖是依實際經緯度轉換的精確海岸線路徑，工程量極大；本次改用「示意配置圖」(相對位置合理但非精確經緯度)，並在每張圖說誠實標註「示意圖，非精確經緯度／非導航路線」，避免誤導。景點照片卡僅對4個已核實存在的Wikimedia Commons檔案(灰姑娘城堡、普羅米修斯火山、新倉山淺間公園忠靈塔、河口湖逆さ富士)放真實連結，其餘一律用灰色色塊卡呈現重點說明，不編造圖檔URL。
- 查證：Disney快速通關(DPA/PP/Standby/Entry Request)、官方飯店比較沿用舊專案已查證資料；新查證項目包含新宿↔河口湖IC路線/過路費/時間(高速.jp)、中央道チェーン規制區間(国交省)、忍野八海/西湖/精進湖周邊資訊(じゃらん、忍野村観光協会)、迪士尼舞浜交通時間。
- Outcome：output/東京迪士尼與河口湖自駕行程_2027年1月版_v1.html 已產出並複製進「一月」資料夾的 output/；HTML結構已用python做tag平衡檢查(section/div/svg/table/li皆平衡)。舊「東京遊」專案的鎖定事實已併入本專案 .context/reference.md，河口湖景點清單v3(含查證/訂正紀錄)與靜岡富士山景點清單v1原文保留在 input/ 兩份交接檔內供查對，未整份複製進 reference.md(避免超出budget，之後若需要可再摘錄)。
- Next：使用者決定河口湖自駕天數與順序後，回頭調整本檔案日期標示；Day1–4/7–9 待使用者自行排定。

## 2026-08-23（續）— 河口湖交通方式改版 v1→v2 + 加Google Map連結
- What：使用者決定河口湖不要全程自駕，改為「新宿搭電車/巴士到河口湖駅→當地才租車自駕→2天1夜」。查證新宿↔河口湖駅交通：JR特急「富士回遊」新宿直達河口湖駅，最速1h53、¥4,200(2026/3改定後，全車指定席)；高速巴士バスタ新宿發，約1h35–45、¥2,200(全席預約制)。河口湖駅周辺租車行：ニッポンレンタカー河口湖駅前店(出站徒歩1–2分)、トヨタレンタカー富士河口湖店(徒歩約7分)，2天報價未逐一核實，需自行比價。據此改寫成 output/東京迪士尼與河口湖自駕行程_2027年1月版_v2.html：把原本的方案A(1日自駕往返)/方案B(1泊2日自駕)合併簡化成單一確定的「河口湖 2天1夜」模組(Day1新宿→河口湖駅取車→北岸+富士吉田；Day2清晨逆富士→西湖精進湖→忍野八海→河口湖駅還車→新宿)，總覽頁地圖/表格、guide頁交通比較與租車資訊、預算表都同步更新。v1保留在output/供比較，未刪除。
- What(追加)：使用者要求每個景點卡加上連結，改用Google Map即可。用python腳本批次處理33張景點卡：抽取<b>景點名</b>文字，產生 https://www.google.com/maps/search/?api=1&query=<景點名 URL編碼> 連結；原本4張有真實Wikimedia圖片的卡片(用<a>包整張卡連結到Commons)改成<div>包裹(避免<a>巢狀<a>的無效HTML)，圖片來源連結移到卡片內文字連結「📷 圖片來源」，另加「📍 Google Map」連結；其餘29張純色塊卡片只加Google Map連結。新增.pgeo CSS樣式。
- Why：使用者實際決定的交通安排改變(不想在東京市區自駕、只想去河口湖當地才租車)；景點連結方便使用者出發前或旅途中直接點開Google Map導航/確認位置，比自製示意SVG地圖更實用可靠。
- 查證/驗證：改版後用python檢查v2 HTML的a/div/svg/section/figure標籤是否平衡(結果全部平衡)，並確認33個pcard都成功加上pgeo連結區塊。Google Map連結是「搜尋」形式(query=景點名)，非精確座標pin，因為沒有逐一核實每個景點的正確GPS座標——搜尋連結對大部分知名地標/店家足夠準確，但少數同名或小眾地點可能需要使用者自行在地圖上確認是否為正確結果。
- Outcome：output/東京迪士尼與河口湖自駕行程_2027年1月版_v2.html 已產出並複製進「一月」資料夾的output/，為目前採用版本。.context/reference.md 的 R7 已更新為交通方式LOCKED；todo.md 移除「決定河口湖1日vs1泊2日」待辦(已定案為2天1夜)，新增「租車報價/回程票需自行確認」待辦。
- Next：使用者決定迪士尼與河口湖的先後順序後，回頭調整v2的日期標示；若要對個別Google Map連結的準確性把關，可挑幾個地標實際點開驗證。

## 2026-10-26 — 套用「東京遊」最新進度到「一月」工作區
- What：使用者把「東京遊」專案資料夾搬進 一月/東京遊/，要求以東京遊進度為最新並套用。舊的一月 progress/todo/reference 備份到 .context/on-demand/archive-2026-10-26_一月舊版/，再以 東京遊/.context 三檔覆蓋；三檔表頭加註路徑約定（output/input/coord 指 東京遊/ 底下）；reference.md 末尾加「一月自身產出已 SUPERSEDED」區塊，並註明本機是 Mac、沒有 gh。
- Why：一月的內容停在 2026-08-23（河口湖 2天1夜、Day1–4/7–9 未定），東京遊已推進到 2026-10-17（全程時間軸定案、住宿與租車已訂）。
- Outcome：一月工作區現行狀態＝東京遊 2026-10-17 狀態。東京遊 journal（93KB）沒有複製，原地保留作為完整歷史。另外發現 claude-skills-md-mods_v1/workspace/projects/東京遊 有一份不完整的副本（缺 input、多數 output），沒有使用。

## 2026-10-26（續）— 交通查證規則＋wrap 同步 GitHub
- What：① 東京遊 claude.md 的交通查證規則（Google Maps＋Gemini 交叉查證）加進 一月/CLAUDE.md（放在 managed 區塊外）。② project-init refresh：managed 區塊與範本相同，未改動。③ 新增 wrap 步驟 6：把 一月/.context 與 東京遊/.context 同步到 ErickLCloud/Ericktrip 的 context/一月/、context/東京遊/。④ 這台 Mac 用 Homebrew 安裝 gh 2.103.2，使用者自己登入 ErickLCloud；repo clone 在 ~/Documents/GitHub/Ericktrip。
- Why：使用者要在不同電腦之間同步進度。
- 取捨：曾建議另開 Private repo（.context 裡有訂位代號、租車預約號）。使用者知道內容會公開後，仍選定 Public 的 Ericktrip。

## 2026-10-26（續2）— Vacation Package 查證＋Day5/6 與 Gemini 共同排程（還沒開始）
- What：使用者說買了迪士尼 Vacation Package，要我和他的 Google Gemini 一起排 Day5/6。在 Gmail 查到確認信 526411274：Enjoy Attractions and More 3DAYS，住 Fantasy Chateau，1/11 入住、住 2 晚、1/13 退房，門票 1/12、1/13，¥443,600；原樂園大飯店 506346459 已取消，**1/13 晚上沒有住宿**。查官方頁得知 Fantasy Chateau 住客兩園都有 Happy Entry（TDL 15 分、TDS 5–15 分），可隨時進 Fantasy Springs。已把這些寫進 reference.md，舊的 Canna／園內餐／Happy Entry 三條加了 ⚠️ 註記。
- 卡關：① claude.ai 的「Gemini」連接器其實是加密貨幣交易所 api.gemini.com，不是 Google Gemini，沒有使用。② 使用者在對話中途接上 Claude in Chrome，但這個對話一直沒出現 Chrome 工具；建議用 `claude --continue --chrome` 重啟。③ Attraction Ticket 選了哪些設施、兩天各去哪個園，使用者還沒提供。
- 使用者決定：1/13 晚上的住宿自己找；Day4 晚餐晚點自己訂。
- Next：接上 Chrome 後，到 gemini.google.com 讓 Gemini 先獨立排一版，再交叉比對。

## 2026-10-26（續3）— 從 Gemini 對話取得 Vacation Package 內容
- What：用 Claude in Chrome 打開 gemini.google.com，在對話「東京迪士尼假期套票優勢」(be574da0e2886538) 找到使用者上傳的兩張 Package 預約畫面截圖。內容：1/12 去 TDL（美女與野獸 10:30、杯麵 14:00、東街咖啡館 12:10、北齋 17:40、TDL 適用設施 ×1），1/13 去 TDS（冰雪奇緣 09:30、小飛俠 11:00、卡納雷托 12:30、麥哲倫 17:00、TDS 適用設施 ×1），兩天早餐都在 Fantasy Springs Restaurant，合計 ¥443,600。使用者確認已把 1/12 早餐從 07:40 改成 06:40。已寫進 reference.md「Vacation Package 已選內容」，「Day5/Day6 園區」改成 1/12 TDL、1/13 TDS（LOCKED）。
- Why：Package 的設施和餐廳已經綁定園區，所以先前建議的 1/12 TDS、1/13 TDL 不能再用。
- 注意：1/12 是 Fantasy Chateau 住客在 TDL 的 Happy Entry 對象外日，所以 Day5 在樂園沒有提早入園。Gemini 在那則對話裡以為有，這部分不採用。
- notes 清空：Gemini 第 1 輪（迪士尼夢幻泉鄉攻略 f2a7b4c4d07a8e4e）排的是 1/12 TDS、1/13 TDL，園區對調後那版作廢；當時用官方頁核對出的錯誤：Believe 和飛濺山 1 月休止、40 週年 Priority Pass 已停止、「神奇的夢幻泉鄉護照」停售沒有來源、TDL 入園時間寫錯。

## 2026-10-26（續4）— Day5/6 與 Gemini 協作、My Booking 核對、時間表 v1→v2
- What：① 用 Chrome 把全程行程打字給 Gemini（不上傳檔案），用 Argon/3.1 Pro 多輪追問 Day5/6。② 讀使用者已登入的 My Booking（526411274，只看不改）：設施/餐廳時段與記錄一致；Itinerary 頁 1/12 早餐仍顯示 07:40，使用者確認已改 06:40；套票另含爆米花桶券、商品券、飲料券。③ 產出 output/迪士尼Day5-6時間表_v1.md，再依使用者決定（1/13 晚餐麥哲倫→Canaletto、午餐→アレンデール・ロイヤルバンケット）出 v2：1/13 改成由北往南單向動線。
- Why：Package 已把園區綁死（1/12 TDL、1/13 TDS），只能排空檔；1 月電氣化鐵路休止，海洋全程步行，所以要避免回頭路。
- 查證：官方 park-restaurant 頁確認皇家宴會廳自 2025/6/1 起是 VP 餐券對象（櫃檯式、自己找位）；FAQ 00067 確認申込期間內可改、費用會變動。我曾誤說皇家宴會廳可預約且是套餐，查官方頁後更正。Gemini 錯誤：40 週年 PP（已停止）、印第安納瓊斯休止（1 月有開）、Standby Pass 可用於設施、海洋 Happy Entry 08:30（實際 8:45 前後）、把 Sky Full of Colors 的休演日套到 Sparkling Jubilee Night、「改便宜餐廳退差額」（它承認原文沒寫）。我也講錯過度假區線站序，Gemini 沒查就附和。
- 新發現：Station Delivery 在 Welcome Center 領取只到 21:00，與 21:00 FS 出園衝突 → 行李方案等 1/13 晚住宿決定。
- Outcome：Day5/6 時間表 v2 為現行草稿；待使用者在 My Booking 送出餐廳變更（約 2027/1/1 前，期限是 Gemini 引用、未親自核對）。
