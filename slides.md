---
theme: default
title: 萬物聯網管家 — 期末專題提案
author: 第 9 組
colorSchema: light
aspectRatio: 16/9
canvasWidth: 980
fonts:
  sans: Inter, Noto Sans TC
  mono: JetBrains Mono
  provider: none
exportFilename: butler-of-everything-proposal
layout: none
transition: fade
---

<div class="deck cover">
<div class="cv-l">
<div class="kick"><span class="dot"></span> 期末專題提案 · 第 9 組 · IoT SYSTEM</div>
<div class="cv-t">萬物聯網管家</div>
<div class="cv-zh">Butler of Everything</div>
<div class="cv-s">以大型語言模型 (LLM) 與 oneM2M 服務層為核心的智慧居家大腦：<br/>用一句自然語言，讓邊緣致動器依指定的時間順序彈性運作。</div>
<div class="cv-m">物聯網技術與應用 (IoT Technologies and Applications) · 2026 年秋季<br/>組員：徐瑞利 · 陳羿豪 · 孫悅騫</div>
</div>
<div class="cv-r">
<div class="cv-terminal-header">
<span>● LIVE SESSION / CHAT-IPE</span>
<span class="mono">CSE:8282</span>
</div>
<div class="bub u">窗簾拉到 1/3，烤箱預熱 200 度，冷氣 23 度開十分鐘後改 25 度，燈一小時後關掉，隔十分鐘再打開。</div>
<div class="bub b">⚡ <b>意圖解析完成：</b>5 個裝置 · 7 個時序步驟。<br/><span style="color:#b45309;font-weight:600">⚠️ 烤箱為高風險加熱裝置，需確認執行？</span></div>
<div class="bub u">確認。</div>
<div class="bub b">✅ <b>計畫 p-42 啟動</b>，首步：窗簾伺服 → 60° (1/3)</div>
<div class="chips">
<span class="chip">💡 燈泡 (GPIO/繼電器)</span>
<span class="chip">🪟 窗簾 (PWM 伺服)</span>
<span class="chip">🔔 蜂鳴器</span>
<span class="chip virt">♨️ 烤箱 (虛擬熱模)</span>
<span class="chip virt">❄️ 冷氣 (虛擬空調)</span>
</div>
</div>
</div>

<!--
大家好，我們是第九組，成員有徐瑞利、陳羿豪和孫悅騫。今天要報告的期末專題，叫做「萬物聯網管家」。簡單說，就是你對家裡說一句話，管家就會聽懂，並且依照你指定的時間順序，去控制燈、窗簾、冷氣和烤箱。右邊這段對話就是一個例子，接下來我們會一步一步說明怎麼做。
-->

---
layout: none
---

<div class="deck">
<div class="hd"><span class="no">1</span><span class="sec">描述 Description</span><span class="grp">萬物聯網管家 · 第 9 組</span></div>
<div class="ttl">一句話輸入，產生有時間順序的居家流程</div>
<div class="bd">
<div class="row g16" style="height:100%">
<div class="col f1 g12">
<div class="card bar"><div class="h3"><span class="tag r">痛點</span> 傳統智慧家庭的碎片化操作</div><div class="p">現有裝置多半需在專屬 App 中逐一設定，或受限於固定的巨集情境。像「冷氣 23 度開 10 分鐘後改 25 度」、「燈關 1 小時後再開」這類具<span class="b">相對時間延遲與順序</span>的複合需求，無法透過一句自然語言即時彈性排程。</div></div>
<div class="card bar a"><div class="h3 a"><span class="tag a">核心構想</span> 自然語言意圖 → 結構化時序計畫</div><div class="p">透過大型語言模型 (LLM) Tool-Calling 將對話直接轉譯為確定性的<span class="b">時序計畫 (Time-Sequenced Plan)</span>；專屬計畫引擎 (Plan Engine) 嚴格計時，透過標準 <span class="b">oneM2M</span> 協定控制實體硬體並閉環回報狀態。</div></div>
<div class="card bar g"><div class="h3 g"><span class="tag g">關鍵優勢</span> 為什麼選擇 oneM2M 標準服務層</div><div class="p">提供統一的資源樹 (AE · container · contentInstance)、透過訂閱 (subscription) 實現事件即時回饋，並以存取控制政策 (ACP) 與不可竄改的 AUDIT 軌跡確保安全。</div></div>
</div>
<div class="col g12" style="width:330px">
<div class="card soft"><div class="h3">主題定位 Topic</div><div class="p b" style="color:#0284c7">建立在 oneM2M 之上的對話式居家管家，具備計畫持久化、安全上限與完整稽核。</div></div>
<div class="card"><div class="h3">邊緣裝置陣容 Devices</div>
<div class="li">💡 <span class="b">燈泡</span>：LED / 數位繼電器控制開關</div>
<div class="li">🪟 <span class="b">窗簾</span>：PWM 微型伺服馬達 (0°–180°)</div>
<div class="li">🔔 <span class="b">蜂鳴器</span>：警示音與「預熱就緒」提示</div>
<div class="li a">♨️❄️ <span class="b">烤箱與冷氣</span>：虛擬熱模型（課堂安全）</div></div>
<div class="card"><div class="h3">延續課堂實驗 Evolution</div><div class="sm"><span class="b">Lab 4–5 基礎：</span>OM2M IN/MN-CSE、Node-RED 橋接、Arduino Uno WiFi Rev2。<br/><span class="b" style="color:#0284c7">課外新增突破：</span>LLM 工具調用、MCP 協定伺服器、高精度時序計畫引擎。</div></div>
</div>
</div>
</div>
<div class="ft"><span>物聯網技術與應用 · 期末專題提案 · 2026 秋</span><span>{{ $slidev.nav.currentPage }} / {{ $slidev.nav.total }}</span></div>
</div>

<!--
先講我們想解決的問題。現在的智慧家庭，大多是一個裝置一個裝置在 App 裡操作，或是套用固定的情境模式。可是如果我想說「冷氣先開 23 度，十分鐘後改成 25 度」，或是「燈一小時後關掉，隔十分鐘再打開」，就得手動設定很多步，臨時想改也很麻煩。我們的想法是：在聊天視窗裡直接用講的，由大型語言模型，也就是 LLM，把這句話轉成有時間順序的計畫，再由計畫引擎一步一步，透過 oneM2M 去控制真正的裝置，做完還會回報實際的狀態。為什麼選 oneM2M？因為它有統一的裝置模型，可以用訂閱取得回饋，還有存取控制政策，也就是 ACP，可以管理誰能做什麼。右邊是我們用的裝置：燈泡、窗簾用的小型伺服馬達、蜂鳴器是實體；烤箱和冷氣用虛擬裝置，因為市電加熱設備不適合在課堂示範。這個專題延續 Lab 4 和 Lab 5 的 OM2M、Node-RED 和 Arduino，再加上課外的 LLM API、MCP 和計畫引擎。
-->

---
layout: none
---

<div class="deck">
<div class="hd"><span class="no">1</span><span class="sec">描述 Description</span><span class="grp">萬物聯網管家 · 第 9 組</span></div>
<div class="ttl">功能：你說什麼，管家怎麼規劃</div>
<div class="bd">
<div class="row g16" style="height:100%">
<div class="col" style="width:510px">
<div class="h3">範例：自然語言意圖 → 結構化致動計畫</div>
<div class="tb"><div class="tr th" style="grid-template-columns:190px 1fr"><div class="td"><div>自然語言輸入</div></div><div class="td"><div>解析為 oneM2M 計畫步驟</div></div></div>
<div class="tr" style="grid-template-columns:190px 1fr"><div class="td"><div class="b">窗簾拉到 1/3</div></div><div class="td"><div><span class="mono">curtain.set(pos = 0.33)</span>（伺服馬達轉動至約 60°）</div></div></div>
<div class="tr" style="grid-template-columns:190px 1fr"><div class="td"><div class="b">烤箱預熱到 200 度</div></div><div class="td"><div><span class="mono">oven.preheat(200)</span>，就緒時蜂鳴器提示，附自動關閉計時</div></div></div>
<div class="tr" style="grid-template-columns:190px 1fr"><div class="td"><div class="b">冷氣 23 度，10 分鐘改 25 度</div></div><div class="td"><div><span class="mono">ac.set(23)</span> 於 +0m，<span class="mono">ac.set(25)</span> 於 +10m</div></div></div>
<div class="tr" style="grid-template-columns:190px 1fr"><div class="td"><div class="b">燈一小時後關，隔 10 分再開</div></div><div class="td"><div><span class="mono">light.off</span> 於 +60m，<span class="mono">light.on</span> 於 +70m</div></div></div>
</div>
<div class="card soft a" style="margin-top:12px"><div class="sm"><span class="b" style="color:#b45309">核心彈性：</span>支援相對延遲 (delay)、保持後還原 (revert)、重複循環與事件觸發（烤箱達標）。指令邏輯完全由後端計畫引擎排程，<span class="b">換任何說法皆無需重新燒錄 Arduino 韌體</span>。</div></div>
</div>
<div class="col f1">
<div class="h3">六大核心功能模組</div>
<div class="grid" style="grid-template-columns:1fr 1fr;gap:10px">
<div class="card" style="padding:10px 12px"><span class="tag t">F1</span> <span class="b sm">語言轉計畫</span><div class="xs mute" style="margin-top:3px">LLM Tool-Calling 嚴格 Schema 驗證</div></div>
<div class="card" style="padding:10px 12px"><span class="tag t">F2</span> <span class="b sm">定時與時序驅動</span><div class="xs mute" style="margin-top:3px">支援延遲 · 保持 · 還原 · 重複調度</div></div>
<div class="card" style="padding:10px 12px"><span class="tag t">F3</span> <span class="b sm">雙向狀態回饋</span><div class="xs mute" style="margin-top:3px">發出指令 vs 硬體反饋狀態即時比對</div></div>
<div class="card" style="padding:10px 12px"><span class="tag t">F4</span> <span class="b sm">動態計畫管理</span><div class="xs mute" style="margin-top:3px">透過自然語言即時查詢、修改與中止</div></div>
<div class="card" style="padding:10px 12px"><span class="tag r">F5</span> <span class="b sm" style="color:#be123c">安全防護 Safety</span><div class="xs mute" style="margin-top:3px">物理上限截斷 · 高風險確認 · 強制關閉</div></div>
<div class="card" style="padding:10px 12px"><span class="tag r">F6</span> <span class="b sm" style="color:#be123c">權限與稽核軌跡</span><div class="xs mute" style="margin-top:3px">ACP 角色防護 · 全歷程寫入 AUDIT</div></div>
</div>
</div>
</div>
</div>
<div class="ft"><span>物聯網技術與應用 · 期末專題提案 · 2026 秋</span><span>{{ $slidev.nav.currentPage }} / {{ $slidev.nav.total }}</span></div>
</div>

<!--
這一頁是功能。左邊四個例子，就是我們想做到的：窗簾拉到三分之一，對應到伺服馬達大約 60 度；烤箱預熱到 200 度，好了蜂鳴器會響，而且有自動關閉的安全計時器；冷氣 23 度，十分鐘後改 25 度；燈一小時後關、隔十分鐘再開。重點是，LLM 只負責把句子轉成結構化的步驟，所以換一種說法、換一種時間安排，Arduino 都不需要重新燒錄。右邊是六個核心功能：語言轉計畫、定時執行、狀態回饋、計畫管理，還有安全防護與權限稽核，後兩項是我們特別想強調的。
-->

---
layout: none
---

<div class="deck">
<div class="hd"><span class="no">2</span><span class="sec">相關研究 Related Work · 1/4 遠距 Distant</span><span class="grp">萬物聯網管家 · 第 9 組</span></div>
<div class="ttl">遠距：市售智慧家庭助理與例行程序</div>
<div class="bd big">
<div class="row g16" style="height:100%">
<div class="col f1 g12">
<div class="card bar"><div class="h3">現有市售產品生態 What exists</div>
<div class="li">主流語音助理與生態系：Amazon Alexa、Google Home、Apple Home (Matter)。</div>
<div class="li">例行程序 (Routines) 與自動化：靜態排程、單一感測條件觸發、IFTTT 式關聯。</div></div>
<div class="card bar a"><div class="h3 a">與本系統之共通點 Relevance</div><div class="p">同樣以「人機自然對話控制多樣家庭設備」為核心體驗，涵蓋燈光、窗簾、冷暖空調等常見家庭負載。</div></div>
<div class="card bar r"><div class="h3 r">關鍵落差與架構侷限 Gap</div>
<div class="li">封閉黑箱生態系：具時間順序的複雜排程多需手動在 App 表單中繁瑣配置，無法靠一句話臨機動態編排。</div>
<div class="li">資料模型與權限不對外公開，缺乏開放的標準服務層供客製化擴充與深度審查。</div></div>
</div>
<div class="col" style="width:310px">
<div class="card soft" style="height:100%"><div class="h3">架構定位小結 Takeaway</div><div class="p" style="font-size:15px">我們汲取其直覺的<span class="b" style="color:#0284c7">人機互動體驗</span>，摒棄其封閉的黑箱架構。</div><div class="sm" style="margin-top:16px;line-height:1.6;color:#334155">本系統將所有裝置節點、時序計畫、致動指令與安全稽核皆透明化為 <span class="b" style="color:#0284c7">oneM2M 標準資源</span>，具備完整可觀測性與二次開發彈性。</div></div>
</div>
</div>
</div>
<div class="ft"><span>物聯網技術與應用 · 期末專題提案 · 2026 秋</span><span>{{ $slidev.nav.currentPage }} / {{ $slidev.nav.total }}</span></div>
</div>

<!--
接下來是相關研究，我們分成遠、中、近三個距離。最遠的是市面上的智慧家庭助理，像 Alexa、Google Home、Apple Home，還有各種例行程序。它們跟我們目標一樣，都是用說的控制家裡，但多半是各家封閉的生態系，有時間順序的流程通常得靠 App 表單或固定模板來設定，資源和權限也不開放給我們檢視。所以我們借用的是它們的使用體驗，不是架構。
-->

---
layout: none
---

<div class="deck">
<div class="hd"><span class="no">2</span><span class="sec">相關研究 Related Work · 2/4 中距 Intermediate</span><span class="grp">萬物聯網管家 · 第 9 組</span></div>
<div class="ttl">中距：用大型語言模型控制智慧家庭與物聯網</div>
<div class="bd big">
<div class="grid" style="grid-template-columns:repeat(3,1fr);gap:12px">
<div class="card bar v"><div class="h3 v">Sasha 代理架構</div><div class="sm"><span class="b">King 等人，ACM IMWUT 2024。</span>運用 LLM 推理處理模糊語意需求（如「讓房間舒服一點」），依硬體能力動態生成操作動作。</div><div class="xs mute" style="margin-top:8px"><span class="b" style="color:#b45309">本案區隔：</span>著重意圖推理；未採用 oneM2M 標準服務層，且缺少具時序性、持久化與安全上限的計畫。</div></div>
<div class="card bar v"><div class="h3 v">Home Assistant + LLM</div><div class="sm">開源智慧家庭平台外掛對話代理 (Conversation Agent)，以語音或文字介面控制已接入之硬體實體。</div><div class="xs mute" style="margin-top:8px"><span class="b" style="color:#b45309">本案區隔：</span>屬於 Home Assistant 自有整合生態，非電信與物聯網國際標準之 oneM2M 服務層架構。</div></div>
<div class="card bar v"><div class="h3 v">IoT-MCP 橋接協定</div><div class="sm"><span class="b">arXiv 2510.01260。</span>藉由 Model Context Protocol (MCP) 連接通用物聯網系統，使模型得以直接調用裝置工具。</div><div class="xs mute" style="margin-top:8px"><span class="b" style="color:#b45309">本案區隔：</span>屬通用型協定轉換；缺少 oneM2M 語意資源樹、細粒度 ACP 存取權限與時序計畫語意。</div></div>
</div>
<div class="card soft" style="margin-top:14px"><div class="h3">學術與工程小結 Takeaway</div><div class="p">「<span class="b" style="color:#0284c7">LLM → 工具 (Tool Calling) → 實體硬體</span>」之技術鏈路已獲充分驗證。然而標準化物聯網仍缺乏：<span class="b" style="color:#0284c7">標準化中介服務層 (oneM2M)</span>、跨越單次請求的<span class="b">高精度時序計畫引擎</span>，以及深植於資料結構內的<span class="b">安全防護與可審計性</span>。</div></div>
</div>
<div class="ft"><span>物聯網技術與應用 · 期末專題提案 · 2026 秋</span><span>{{ $slidev.nav.currentPage }} / {{ $slidev.nav.total }}</span></div>
</div>

<!--
中距離的是用大型語言模型控制智慧家庭或物聯網的研究和專案。像 Sasha 處理的是意圖不明確的需求，例如「讓房間舒服一點」；Home Assistant 有 LLM 對話代理；IoT-MCP 則讓模型透過 MCP 直接呼叫裝置工具。這些都證明「LLM 呼叫工具再控制裝置」這個模式可行，但它們不是建立在 oneM2M 服務層上，也比較少處理跨時間的計畫、安全限制和稽核。
-->

---
layout: none
---

<div class="deck">
<div class="hd"><span class="no">2</span><span class="sec">相關研究 Related Work · 3/4 近距 Close</span><span class="grp">萬物聯網管家 · 第 9 組</span></div>
<div class="ttl">近距：MCP 遇上 oneM2M 國際標準</div>
<div class="bd big">
<div class="row g16" style="height:100%">
<div class="col f1 g12">
<div class="card bar"><div class="h3">oneM2M TR-0081 與 WI-0122 標準化進程</div>
<div class="li">oneM2M 組織正積極制定 MCP 與 oneM2M 互通規範 (Interworking)。</div>
<div class="li">代理層（「MCP-IPE」）介於 MCP 用戶端與 CSE 間；每個代理綁定單一 oneM2M 身分權杖。</div>
<div class="li">採取「預設拒絕 (Deny-by-Default)」原則，最終授權動作交由 CSE ACP 裁決。</div></div>
<div class="card bar"><div class="h3">onem2m-mcp v0.4.1（開源專案，2026 年 8 月）</div>
<div class="li">提供 17 個標準 MCP 工具：涵蓋資源探索、建立 container、寫入 contentInstance、訂閱等。</div>
<div class="li">支援 TLS 與 OAuth 2.1 權杖驗證機制；主要驗證環境為 ACME CSE，OM2M 列為相容。</div></div>
</div>
<div class="col" style="width:340px">
<div class="card soft a" style="height:100%"><div class="h3 a">沿用什麼 vs 本專題四大創新突破</div>
<div class="li a"><span class="b" style="color:#0f172a">傳承借鏡：</span>代理身分綁定與預設拒絕的安全原則。</div>
<div class="li a"><span class="b" style="color:#b45309">創新 1：時序計畫引擎</span><br/>突破單步調用，實現跨時間軸之排程生命週期。</div>
<div class="li a"><span class="b" style="color:#b45309">創新 2：實體邊緣硬體閉環</span><br/>於 Arduino + OM2M 實驗室環境完成端到端落地。</div>
<div class="li a"><span class="b" style="color:#b45309">創新 3：系統級安全防護網</span><br/>參數限幅、強制二次確認、加熱設備超時熔斷。</div>
<div class="li a"><span class="b" style="color:#b45309">創新 4：量化基準評估</span><br/>語意轉譯精確率與計時器 Jitter 誤差實測。</div></div>
</div>
</div>
</div>
<div class="ft"><span>物聯網技術與應用 · 期末專題提案 · 2026 秋</span><span>{{ $slidev.nav.currentPage }} / {{ $slidev.nav.total }}</span></div>
</div>

<!--
最接近的是 oneM2M 組織自己正在做的 MCP 與 oneM2M 互通。TR-0081 和 WI-0122 描述了代理層，每個代理綁定一個 oneM2M 身分，而且預設拒絕、最後由 CSE 決定授權。另外還有開源套件 onem2m-mcp，目前版本 0.4.1，提供 17 個工具，主要在 ACME 這個 CSE 上測試，OM2M 只是列為相容。我們沿用它們的身分和預設拒絕的想法，再補上四件事：處理時間順序的計畫引擎、在課堂硬體上真的動起來的致動鏈、裝置層級的安全機制，以及對正確率和時間精度的量化評估。
-->

---
layout: none
---

<div class="deck">
<div class="hd"><span class="no">2</span><span class="sec">相關研究 Related Work · 4/4 獨特優勢 Unique advantages</span><span class="grp">萬物聯網管家 · 第 9 組</span></div>
<div class="ttl">獨特優勢：與現有方案的多維度綜合比較</div>
<div class="bd">
<div class="tb cmp">
<div class="tr th" style="grid-template-columns:310px repeat(4, 1fr)"><div class="td"><div>系統核心能力與技術指標</div></div><div class="td"><div>商業雲端助理</div></div><div class="td"><div>LLM + HA / 研究</div></div><div class="td"><div>onem2m-mcp</div></div><div class="td"><div>萬物聯網管家 (本專題)</div></div></div>
<div class="tr" style="grid-template-columns:310px repeat(4, 1fr)"><div class="td"><div>oneM2M 服務層架構 (AE · cnt · ACP)</div></div><div class="td"><div class="none c f1">–</div></div><div class="td"><div class="none c f1">–</div></div><div class="td"><div class="yes c f1">●</div></div><div class="td"><div class="yes c f1">●</div></div></div>
<div class="tr" style="grid-template-columns:310px repeat(4, 1fr)"><div class="td"><div>自然語言端到端控制硬體</div></div><div class="td"><div class="yes c f1">●</div></div><div class="td"><div class="yes c f1">●</div></div><div class="td"><div class="yes c f1">●</div></div><div class="td"><div class="yes c f1">●</div></div></div>
<div class="tr" style="grid-template-columns:310px repeat(4, 1fr)"><div class="td"><div>一句話生成時序計畫 (延遲 · 保持 · 還原)</div></div><div class="td"><div class="part c f1">◐</div></div><div class="td"><div class="part c f1">◐</div></div><div class="td"><div class="none c f1">–</div></div><div class="td"><div class="yes c f1">●</div></div></div>
<div class="tr" style="grid-template-columns:310px repeat(4, 1fr)"><div class="td"><div>實體邊緣硬體致動鏈 (Arduino / 伺服 / 燈)</div></div><div class="td"><div class="yes c f1">●</div></div><div class="td"><div class="yes c f1">●</div></div><div class="td"><div class="none c f1">–</div></div><div class="td"><div class="yes c f1">●</div></div></div>
<div class="tr" style="grid-template-columns:310px repeat(4, 1fr)"><div class="td"><div>裝置安全防護網 (上限裁切 · 確認 · 自動關閉)</div></div><div class="td"><div class="part c f1">◐</div></div><div class="td"><div class="part c f1">◐</div></div><div class="td"><div class="none c f1">–</div></div><div class="td"><div class="yes c f1">●</div></div></div>
<div class="tr" style="grid-template-columns:310px repeat(4, 1fr)"><div class="td"><div>獨立代理身分與細粒度 ACP 存取控制</div></div><div class="td"><div class="part c f1">◐</div></div><div class="td"><div class="part c f1">◐</div></div><div class="td"><div class="yes c f1">●</div></div><div class="td"><div class="yes c f1">●</div></div></div>
<div class="tr" style="grid-template-columns:310px repeat(4, 1fr)"><div class="td"><div>全生命週期稽核日誌 (存為 oneM2M 資源)</div></div><div class="td"><div class="none c f1">–</div></div><div class="td"><div class="none c f1">–</div></div><div class="td"><div class="none c f1">–</div></div><div class="td"><div class="yes c f1">●</div></div></div>
</div>
<div class="row ai-c" style="justify-content:space-between;margin-top:12px">
<div class="xs mute">● 完整支援 · ◐ 部分支援或受限廠商 · – 未提供或非核心。依公開規格與文獻整理。</div>
<div class="row g10 ai-c">
<span class="tag t b">1. 開放 oneM2M 服務層</span>
<span class="tag a b">2. 跨時序排程生命週期</span>
<span class="tag r b">3. 預設多層安全稽核</span>
</div>
</div>
</div>
<div class="ft"><span>物聯網技術與應用 · 期末專題提案 · 2026 秋</span><span>{{ $slidev.nav.currentPage }} / {{ $slidev.nav.total }}</span></div>
</div>

<!--
這張表是我們和現有方案的比較。符號是依公開文件整理的，橫線代表對方沒有把它列為重點，不是說做不到。我們有三個特點：第一，一切都是 oneM2M 資源，開放而且標準；第二，我們做的是計畫，可以儲存、修改、取消，不是一次性的指令；第三，安全是設計的一部分，有多層防護和稽核紀錄。
-->

---
layout: none
---

<div class="deck">
<div class="hd"><span class="no">3</span><span class="sec">參與者 Actors</span><span class="grp">萬物聯網管家 · 第 9 組</span></div>
<div class="ttl">參與者：系統層級與角色映射</div>
<div class="bd big">
<div class="tb"><div class="tr th" style="grid-template-columns:210px 1fr 280px"><div class="td"><div>參與實體 / 節點</div></div><div class="td"><div>在本系統中的核心職責</div></div><div class="td"><div>oneM2M 標準架構對應</div></div></div>
<div class="tr" style="grid-template-columns:210px 1fr 280px"><div class="td"><div><span class="b" style="color:#0284c7">住戶 Resident</span></div></div><div class="td"><div>輸入自然語言、確認高風險動作、監看狀態回饋</div></div><div class="td"><div>人類使用者；透過 Butler AE 交互</div></div></div>
<div class="tr" style="grid-template-columns:210px 1fr 280px"><div class="td"><div><span class="b" style="color:#b45309">管家代理 (LLM Agent)</span></div></div><div class="td"><div>自然語言語意解析、調用結構化工具、產出對話回饋</div></div><div class="td"><div>AE「Butler」背後的智慧應用邏輯</div></div></div>
<div class="tr" style="grid-template-columns:210px 1fr 280px"><div class="td"><div><span class="b" style="color:#7c3aed">工具伺服器 + 計畫引擎</span></div></div><div class="td"><div>Schema 校驗、角色權限檢查、精準時間調度與狀態核對</div></div><div class="td"><div>具備 MCP-IPE 角色之專用 AE (TR-0081)</div></div></div>
<div class="tr" style="grid-template-columns:210px 1fr 280px"><div class="td"><div><span class="b" style="color:#059669">OM2M CSE 服務層</span></div></div><div class="td"><div>資源樹維護、ACP 授權判定、狀態持久化與 AUDIT 日誌</div></div><div class="td"><div>群組 VM 部署之 MN-CSE (:8282) 與 IN-CSE (:8080)</div></div></div>
<div class="tr" style="grid-template-columns:210px 1fr 280px"><div class="td"><div><span class="b">Node-RED 閘道橋接</span></div></div><div class="td"><div>oneM2M 資源與 Arduino HTTP 轉發、指令隊列緩衝</div></div><div class="td"><div>Interworking Proxy 網關應用 (IPE)</div></div></div>
<div class="tr" style="grid-template-columns:210px 1fr 280px"><div class="td"><div><span class="b">Arduino 邊緣節點</span></div></div><div class="td"><div>驅動實體燈泡、伺服馬達（窗簾）與蜂鳴器，即時回傳狀態</div></div><div class="td"><div>ADN (Application Dedicated Node)</div></div></div>
<div class="tr" style="grid-template-columns:210px 1fr 280px"><div class="td"><div><span class="b" style="color:#b45309">虛擬裝置 Virtual Devs</span></div></div><div class="td"><div>以一階熱物理模型模擬烤箱與冷氣之升降溫與維持</div></div><div class="td"><div>模擬 AE，資料結構與實體裝置完全一致</div></div></div>
</div>
</div>
<div class="ft"><span>物聯網技術與應用 · 期末專題提案 · 2026 秋</span><span>{{ $slidev.nav.currentPage }} / {{ $slidev.nav.total }}</span></div>
</div>

<!--
從這頁開始，是 TR-0001 格式的使用案例。先看參與者：住戶是使用者；管家代理就是 LLM，負責理解和說明；工具伺服器加計畫引擎是核心後端，負責驗證、套用安全規則、準時發出每一步；OM2M 的 MN-CSE 和 IN-CSE 存放資源並做存取控制；Node-RED 是連接 oneM2M 和 Arduino 的橋接；Arduino 負責實體裝置；烤箱和冷氣是虛擬裝置，資源格式和真實裝置一樣，之後有硬體可以直接換。
-->

---
layout: none
---

<div class="deck">
<div class="hd"><span class="no">4</span><span class="sec">前置條件 Preconditions</span><span class="grp">萬物聯網管家 · 第 9 組</span></div>
<div class="ttl">前置條件：系統就緒檢查清單</div>
<div class="bd big">
<div class="grid" style="grid-template-columns:1fr 1fr;gap:16px">
<div class="card bar"><div class="h3"><span class="tag t">架構</span> 基礎設施與網路節點就緒</div>
<div class="li ck">OM2M IN-CSE (:8080) 與 MN-CSE (:8282) 於 VM 上運行，MN-CSE 已註冊至 IN-CSE。</div>
<div class="li ck">AE「Butler」資源結構建立完畢，包含 CMD, PLAN, POLICY, AUDIT 及各裝置 STATE 容器。</div>
<div class="li ck">Node-RED 流程已部署：指令隊列緩衝、<span class="mono">/next</span> 輪詢端點、<span class="mono">/state</span> 回報端點與虛擬熱模型。</div>
<div class="li ck">Arduino Uno WiFi Rev2 燒錄單一通用韌體並連上實驗室 Wi-Fi；群組 VM 配置固定區域網路 IP。</div></div>
<div class="card bar a"><div class="h3 a"><span class="tag a">規則</span> 安全政策、角色權限與運算環境</div>
<div class="li ck">POLICY 參數載入：烤箱 ≤ 250°C 且 ≤ 120min、伺服限角 0–180°、高風險設備強制二次確認。</div>
<div class="li ck">ACP 角色權限已定義：<span class="mono">viewer</span>（唯讀）與 <span class="mono">operator</span>（讀寫指令）；嚴格禁止任何刪除權限。</div>
<div class="li ck">LLM API 金鑰與 Tool Schema 綁定完成，並備妥本機規則式備援解析器 (Fallback Parser)。</div>
<div class="li ck">後端與 VM 統一採用 NTP 對時；已支援示範時鐘加速倍率（×1 標準速 / ×60 展示速）。</div></div>
</div>
<div class="card soft" style="margin-top:14px"><div class="sm"><span class="b" style="color:#059669">硬體閉環驗證：</span>在啟動任何時序計畫前，燈泡、伺服馬達、蜂鳴器接線已通過單元自檢；全專題開發與展示皆使用同一份通用韌體，無需反覆燒錄。</div></div>
</div>
<div class="ft"><span>物聯網技術與應用 · 期末專題提案 · 2026 秋</span><span>{{ $slidev.nav.currentPage }} / {{ $slidev.nav.total }}</span></div>
</div>

<!--
前置條件分成兩塊。基礎建設方面：OM2M 的 IN 與 MN 已經啟動並註冊，Butler 這個 AE 和各個容器已建立，Node-RED 流程已部署，Arduino 已燒錄通用韌體並連上實驗室 Wi-Fi，VM 使用固定 IP。設定與權限方面：政策容器裡有各裝置的上限，角色分成唯讀和可操作，LLM 金鑰與備援解析器就緒，並設定好示範用的時間加速倍率。
-->

---
layout: none
---

<div class="deck">
<div class="hd"><span class="no">5</span><span class="sec">觸發條件 Triggers</span><span class="grp">萬物聯網管家 · 第 9 組</span></div>
<div class="ttl">觸發條件：事件驅動之物聯網架構</div>
<div class="bd big">
<div class="grid" style="grid-template-columns:repeat(3,1fr);gap:14px">
<div class="card bar"><span class="tag solid">T1</span> <span class="b sm">使用者輸入 User Message</span><div class="sm" style="margin-top:8px">透過交談介面輸入自然語言（網頁即時終端，後續可擴充至 LINE 或語音介面），例如「我要睡了」。</div></div>
<div class="card bar"><span class="tag solid">T2</span> <span class="b sm">計畫步驟到期 Step Due</span><div class="sm" style="margin-top:8px">計畫引擎之高精度排程計時器到達各步驟預定時刻（+10m、+60m、+70m…），觸發下發下一筆指令。</div></div>
<div class="card bar"><span class="tag solid">T3</span> <span class="b sm">裝置事件回饋 Device Event</span><div class="sm" style="margin-top:8px">硬體狀態回報到達、預期回報逾時 (Timeout)，或虛擬烤箱升溫達到目標溫度之就緒事件。</div></div>
<div class="card bar a"><span class="tag solid a">T4</span> <span class="b sm">安全計時熔斷 Safety Timer</span><div class="sm" style="margin-top:8px">高風險加熱裝置運轉時間達到預設最長上限，安全守護機制強制觸發關閉指令。</div></div>
<div class="card bar a"><span class="tag solid a">T5</span> <span class="b sm">動態追蹤變更 Follow-up</span><div class="sm" style="margin-top:8px">執行過程中住戶發出新請求，如「取消冷氣排程」、「改設 24 度」，動態修改或抽換待執行步驟。</div></div>
<div class="card bar a"><span class="tag solid a">T6</span> <span class="b sm">環境感測器事件（選配）</span><div class="sm" style="margin-top:8px">如冷氣運轉期間偵測到門窗接點被開啟，管家自動發送告警提示並執行聯動降載。</div></div>
</div>
<div class="card soft" style="margin-top:14px"><div class="sm"><span class="b" style="color:#0284c7">範圍界定：</span>T1–T5 為本期末專題之標準交付核心範圍；T6 為時間充裕時之進階延伸演練。</div></div>
</div>
<div class="ft"><span>物聯網技術與應用 · 期末專題提案 · 2026 秋</span><span>{{ $slidev.nav.currentPage }} / {{ $slidev.nav.total }}</span></div>
</div>

<!--
什麼會觸發流程？有六種。最核心的兩種是：使用者傳訊息，以及計畫步驟時間到。第三是裝置事件，例如烤箱升到目標溫度，或裝置沒有回應。第四是安全計時器，高風險裝置超過最長運轉時間就自動關閉。第五是使用者中途修改或取消。第六是感測器事件，例如冷氣運轉時窗戶被打開，這是時間夠才做的延伸。
-->

---
layout: none
---

<div class="deck">
<div class="hd"><span class="no">6</span><span class="sec">正常流程 Normal Flow · 1/2</span><span class="grp">萬物聯網管家 · 第 9 組</span></div>
<div class="ttl">正常流程：端到端執行管線</div>
<div class="bd big">
<div class="row g16" style="height:100%">
<div class="col f1">
<div class="st"><div class="stn">1</div><div class="stt"><span class="tag t">住戶</span> 輸入「窗簾拉 1/3，烤箱預熱 200 度，冷氣 23 度開十分鐘改 25 度，燈一小時後關、隔十分鐘再開。」</div></div>
<div class="st"><div class="stn">2</div><div class="stt"><span class="tag v">代理 (LLM)</span> 調用工具 <span class="mono">create_plan</span>，產出標準結構化計畫（裝置、動作、相對時間）。</div></div>
<div class="st"><div class="stn a">3</div><div class="stt"><span class="tag a">工具伺服器</span> 嚴格校驗 Schema、裝置白名單、數值上限與呼叫者角色，回傳可讀摘要。</div></div>
<div class="st"><div class="stn">4</div><div class="stt"><span class="tag v">代理</span> 提示「已規劃 5 個裝置、7 個步驟。烤箱需二次確認，確認執行？」</div></div>
<div class="st"><div class="stn">5</div><div class="stt"><span class="tag t">住戶</span> 回覆「確認」。</div></div>
<div class="st"><div class="stn a">6</div><div class="stt"><span class="tag a">計畫引擎</span> 將計畫寫入 PLAN 容器並在本地註冊高精度計時事件。</div></div>
<div class="st"><div class="stn a">7</div><div class="stt"><span class="tag a">步驟到期</span> 攜帶唯一遞增編號 (id) 將指令寫入 CMD 容器（經由 CSE，綁定代理身分）。</div></div>
<div class="st"><div class="stn">8</div><div class="stt"><span class="tag g">Node-RED + Arduino</span> 提取最新指令完成實體致動，並將實際量測狀態回填至 STATE 容器。</div></div>
<div class="st"><div class="stn a">9</div><div class="stt"><span class="tag a">計畫引擎</span> 核對指令與實際回報是否一致，寫入不可篡改之 AUDIT 紀錄，並通知住戶。</div></div>
</div>
<div class="col" style="width:390px">
<div class="h3"><span class="tag v">JSON Payload</span> 結構化時序計畫</div>
<pre class="code" style="font-size:11px">{
  "plan": "p-42", "by": "operator",
  "steps": [
    {"at":"+0m","dev":"curtain","do":"set","pos":0.33},
    {"at":"+0m","dev":"oven","do":"preheat","temp":200},
    {"at":"+0m","dev":"ac","do":"set","temp":23},
    {"at":"+10m","dev":"ac","do":"set","temp":25},
    {"on":"oven.ready","dev":"buzzer","do":"beep"},
    {"at":"+60m","dev":"light","do":"off"},
    {"at":"+70m","dev":"light","do":"on"}
  ]
}</pre>
<div class="xs mute" style="margin-top:8px;line-height:1.5"><span class="b" style="color:#0284c7">關鍵設計：</span>LLM 僅在解析階段調用一次產出靜態排程，後續計時排程與指令發布全由計畫引擎本地自主執行，大幅降低 API 開銷與延遲。</div>
</div>
</div>
</div>
<div class="ft"><span>物聯網技術與應用 · 期末專題提案 · 2026 秋</span><span>{{ $slidev.nav.currentPage }} / {{ $slidev.nav.total }}</span></div>
</div>

<!--
這是正常流程，一共九步。第一步，住戶講一句話。第二步，LLM 呼叫 create_plan 這個工具，產生右邊這種結構化計畫。第三步，工具伺服器驗證格式、裝置白名單、上限和角色權限。第四、五步，因為有烤箱，管家會先摘要並要求確認，住戶說確認。第六步，計畫引擎把計畫存進 PLAN 並排程。第七步，每個時間到的步驟，都會寫一筆帶編號的指令到 CMD。第八步，Node-RED 和 Arduino 取得指令、動作，並把實際狀態回報到 STATE。第九步，計畫引擎核對指令和實際狀態，寫入稽核，最後通知住戶。要特別說明：LLM 只在一開始用一次，之後的計時和執行都不靠 LLM，所以又便宜又準時。
-->

---
layout: none
---

<div class="deck">
<div class="hd"><span class="no">6</span><span class="sec">正常流程 Normal Flow · 2/2</span><span class="grp">萬物聯網管家 · 第 9 組</span></div>
<div class="ttl">正常流程：時序排程調度軸 (Timeline)</div>
<div class="bd">
<div class="tl">
<div class="tl-ax"><span style="left:0.0%">0 分 (現在)</span><span style="left:12.5%">+10 分</span><span style="left:25.0%">+20 分</span><span style="left:37.5%">+30 分</span><span style="left:50.0%">+40 分</span><span style="left:62.5%">+50 分</span><span style="left:75.0%">+60 分</span><span style="left:87.5%">+70 分</span><span style="left:100.0%;transform:translateX(-100%)">+80 分</span></div>
<div class="tl-lane"><div class="tl-lbl"><div>🪟 窗簾<small>PWM 伺服</small></div></div><div class="tl-ch"><div class="tl-grid" style="left:0.0%"></div><div class="tl-grid" style="left:12.5%"></div><div class="tl-grid" style="left:25.0%"></div><div class="tl-grid" style="left:37.5%"></div><div class="tl-grid" style="left:50.0%"></div><div class="tl-grid" style="left:62.5%"></div><div class="tl-grid" style="left:75.0%"></div><div class="tl-grid" style="left:87.5%"></div><div class="tl-grid" style="left:100.0%"></div><div class="tl-bar t2" style="left:0.0%;width:calc(18.75% - 2px)">轉動至 1/3 (≈ 60°)</div><div class="tl-bar t" style="left:18.75%;width:calc(81.25% - 2px)">持續保持目標角度</div></div></div>
<div class="tl-lane"><div class="tl-lbl"><div>♨️ 烤箱<small>虛擬熱模型</small></div></div><div class="tl-ch"><div class="tl-grid" style="left:0.0%"></div><div class="tl-grid" style="left:12.5%"></div><div class="tl-grid" style="left:25.0%"></div><div class="tl-grid" style="left:37.5%"></div><div class="tl-grid" style="left:50.0%"></div><div class="tl-grid" style="left:62.5%"></div><div class="tl-grid" style="left:75.0%"></div><div class="tl-grid" style="left:87.5%"></div><div class="tl-grid" style="left:100.0%"></div><div class="tl-bar a2" style="left:0.0%;width:calc(18.75% - 2px)">升溫預熱 → 200°C</div><div class="tl-bar a" style="left:18.75%;width:calc(81.25% - 2px)">恆溫維持 200°C · 安全計時防護 ≤ 120 分鐘</div></div></div>
<div class="tl-lane"><div class="tl-lbl"><div>❄️ 冷氣<small>虛擬空調</small></div></div><div class="tl-ch"><div class="tl-grid" style="left:0.0%"></div><div class="tl-grid" style="left:12.5%"></div><div class="tl-grid" style="left:25.0%"></div><div class="tl-grid" style="left:37.5%"></div><div class="tl-grid" style="left:50.0%"></div><div class="tl-grid" style="left:62.5%"></div><div class="tl-grid" style="left:75.0%"></div><div class="tl-grid" style="left:87.5%"></div><div class="tl-grid" style="left:100.0%"></div><div class="tl-bar t2" style="left:0.0%;width:calc(12.5% - 2px)">運轉於 23°C</div><div class="tl-bar t" style="left:12.5%;width:calc(87.5% - 2px)">調控至 25°C 節能模式直至指令更新</div></div></div>
<div class="tl-lane"><div class="tl-lbl"><div>🔔 蜂鳴器<small>事件反饋</small></div></div><div class="tl-ch"><div class="tl-grid" style="left:0.0%"></div><div class="tl-grid" style="left:12.5%"></div><div class="tl-grid" style="left:25.0%"></div><div class="tl-grid" style="left:37.5%"></div><div class="tl-grid" style="left:50.0%"></div><div class="tl-grid" style="left:62.5%"></div><div class="tl-grid" style="left:75.0%"></div><div class="tl-grid" style="left:87.5%"></div><div class="tl-grid" style="left:100.0%"></div><div class="tl-bar v" style="left:18.75%;width:calc(22.0% - 2px)">嗶聲提示：烤箱達標就緒</div></div></div>
<div class="tl-lane"><div class="tl-lbl"><div>💡 燈泡<small>實體 LED</small></div></div><div class="tl-ch"><div class="tl-grid" style="left:0.0%"></div><div class="tl-grid" style="left:12.5%"></div><div class="tl-grid" style="left:25.0%"></div><div class="tl-grid" style="left:37.5%"></div><div class="tl-grid" style="left:50.0%"></div><div class="tl-grid" style="left:62.5%"></div><div class="tl-grid" style="left:75.0%"></div><div class="tl-grid" style="left:87.5%"></div><div class="tl-grid" style="left:100.0%"></div><div class="tl-bar g" style="left:0.0%;width:calc(75.0% - 2px)">維持開啟 (ON)</div><div class="tl-bar off" style="left:75.0%;width:calc(12.5% - 2px)">關閉 (OFF)</div><div class="tl-bar g" style="left:87.5%;width:calc(12.5% - 2px)">重新開啟 (ON)</div></div></div>
</div>
<div class="grid" style="grid-template-columns:repeat(3,1fr);gap:12px;margin-top:14px">
<div class="card" style="padding:9px 13px"><span class="tag a">時間驅動 Time-based</span> <span class="sm">冷氣 +10m、燈泡 +60m / +70m 精準觸發</span></div>
<div class="card" style="padding:9px 13px"><span class="tag v">事件驅動 Event-based</span> <span class="sm">烤箱實測到達 200°C 觸發蜂鳴器響鳴</span></div>
<div class="card" style="padding:9px 13px"><span class="tag g">示範時鐘加速 (×60)</span> <span class="sm">70 分鐘排程於展示時約 70 秒流暢播畢</span></div>
</div>
</div>
<div class="ft"><span>物聯網技術與應用 · 期末專題提案 · 2026 秋</span><span>{{ $slidev.nav.currentPage }} / {{ $slidev.nav.total }}</span></div>
</div>

<!--
同一個計畫，用時間軸來看。時間零的時候，窗簾轉到三分之一，烤箱開始預熱，冷氣設 23 度。第十分鐘，冷氣改成 25 度。烤箱到達溫度時蜂鳴器響，這是事件觸發，不是固定時間。第六十分鐘燈關掉，第七十分鐘再打開。烤箱預熱的時間是模擬值。因為現場不可能真的等一小時，所以我們在政策容器裡設定示範用的時間加速，六十倍的話，七十分鐘大約七十秒就播完。
-->

---
layout: none
---

<div class="deck">
<div class="hd"><span class="no">7</span><span class="sec">替代流程 Alternative Flow</span><span class="grp">萬物聯網管家 · 第 9 組</span></div>
<div class="ttl">替代流程：異常邊界與韌性防護機制</div>
<div class="bd big">
<div class="grid" style="grid-template-columns:repeat(3,1fr);gap:14px">
<div class="card bar"><span class="tag solid">A1</span> <span class="b sm">語意歧義 Ambiguity</span><div class="sm" style="margin-top:6px">如「窗簾拉 1/3」是指開 1/3 還是關 1/3？管家發送單一精準澄清問題，在住戶確認前不發出任何指令。</div></div>
<div class="card bar a"><span class="tag solid a">A2</span> <span class="b sm">越界或不安全參數</span><div class="sm" style="margin-top:6px">如「烤箱 300 度開 6 小時」立即被 Policy 守門攔截，反饋系統上限與替代方案；烤箱一律強制二次確認。</div></div>
<div class="card bar"><span class="tag solid">A3</span> <span class="b sm">權限不足 Denied</span><div class="sm" style="margin-top:6px"><span class="mono">viewer</span> 角色試圖操作時，CSE (ACP) 與工具伺服器直接拒絕，發出警示說明並將非法嘗試記錄於 AUDIT。</div></div>
<div class="card bar a"><span class="tag solid a">A4</span> <span class="b sm">裝置離線或回應逾時</span><div class="sm" style="margin-top:6px">經 2 次重試無 ack 後，標記該步失敗並推播警報；依計畫定義之策略選擇繼續後續獨立步驟或安全終止。</div></div>
<div class="card bar"><span class="tag solid">A5</span> <span class="b sm">執行中撤銷或動態插單</span><div class="sm" style="margin-top:6px">「取消冷氣排程」或同一設備被指派新任務：確認後安全移除待辦佇列；烤箱專屬安全關閉計時器維持有效。</div></div>
<div class="card bar a"><span class="tag solid a">A6</span> <span class="b sm">LLM 服務故障或輸出畸形</span><div class="sm" style="margin-top:6px">格式驗證失敗自動重試；若雲端 API 中斷，無縫啟用本機規則式解析器 (Fallback)，保障常用指令可用。</div></div>
</div>
</div>
<div class="ft"><span>物聯網技術與應用 · 期末專題提案 · 2026 秋</span><span>{{ $slidev.nav.currentPage }} / {{ $slidev.nav.total }}</span></div>
</div>

<!--
替代流程有六種。A1，句子有歧義，例如「窗簾拉 1/3」是開三分之一還是關三分之一，管家只問一句，不先下指令。A2，不安全或超出範圍，例如烤箱 300 度連開六小時，會被防護機制擋下，並提供可接受的選項。A3，權限不足，由 ACP 或工具伺服器拒絕，管家說明原因，也會把這次嘗試記進稽核。A4，裝置離線，重試兩次後標記失敗並通知住戶。A5，使用者修改、取消，或同一個裝置有新計畫，確認後取代舊的。A6，LLM 不能用或輸出格式錯誤，就重試，必要時改用規則式解析器當備援。
-->

---
layout: none
---

<div class="deck">
<div class="hd"><span class="no">8</span><span class="sec">高階示意圖 High-Level Illustration · 1/2</span><span class="grp">萬物聯網管家 · 第 9 組</span></div>
<div class="ttl">高階架構：端到端系統資料拓撲</div>
<div class="bd">
<div class="arch" style="height:216px">
<div class="bx" style="width:116px"><span class="tag solid bt">新增</span><div class="bh">住戶客戶端</div><div class="pill">交談式網頁 UI<br/>(後續擴展 LINE)</div><div class="xs mute">自然語言指令、二次確認</div></div>
<div class="arr">HTTP<br/>REST</div>
<div class="bx new" style="width:184px"><span class="tag solid a bt">新增</span><div class="bh">管家服務核心</div><div class="pill">LLM · Tool-Calling 代理</div><div class="pill">MCP 工具伺服器<br/>格式校驗 · 角色檢查 · 守門</div><div class="pill">時序計畫引擎<br/>高精度排程 · 狀態閉環核對</div></div>
<div class="arr">oneM2M<br/>REST</div>
<div class="bx" style="width:172px"><span class="tag solid bt">Lab 4–5</span><div class="bh">OM2M MN-CSE</div><div class="pill">AE「Butler」資源結構</div><div class="pill">CMD · PLAN · POLICY · AUDIT</div><div class="pill">各裝置獨立 STATE 容器</div><div class="xs mute">向上註冊至 IN-CSE (:8080)</div></div>
<div class="arr">HTTP<br/>輪詢/推送</div>
<div class="bx" style="width:142px"><span class="tag solid bt">Lab 5</span><div class="bh">Node-RED 閘道</div><div class="pill">/next 與 /state 端點</div><div class="pill">指令隊列緩衝處理</div><div class="pill virt">虛擬烤箱 · 冷氣熱模型</div></div>
<div class="arr">Wi-Fi<br/>REST</div>
<div class="bx" style="width:124px"><span class="tag solid bt">Lab 5</span><div class="bh">Arduino Rev2</div><div class="pill">💡 LED 燈泡</div><div class="pill">🪟 伺服馬達 (窗簾)</div><div class="pill">🔔 蜂鳴器提示</div></div>
</div>
<div class="h3 r" style="margin-top:14px">貫穿鏈路的四大安全防護網 Guard Layers</div>
<div class="layers">
<div class="layer"><span class="b" style="color:#be123c">1 身分認證與 ACP</span><br/>代理專屬 Originator 身分，由 CSE 實施存取控制</div>
<div class="layer"><span class="b" style="color:#be123c">2 MCP 守門檢查</span><br/>嚴格工具參數 Schema 檢驗、裝置白名單、強制確認</div>
<div class="layer"><span class="b" style="color:#be123c">3 裝置物理上限防護</span><br/>POLICY 容器約束、韌體限幅裁切、加熱自動超時關閉</div>
<div class="layer"><span class="b" style="color:#be123c">4 不可篡改稽核軌跡</span><br/>每一次請求、執行決策與反饋狀態全數持久化至 AUDIT</div>
</div>
<div class="xs mute" style="margin-top:8px">● 青藍色節點：沿用實驗課基礎設施 · ● 橘色節點：本專題課外自研新增 · 虛線標示：純軟體虛擬熱模型。</div>
</div>
<div class="ft"><span>物聯網技術與應用 · 期末專題提案 · 2026 秋</span><span>{{ $slidev.nav.currentPage }} / {{ $slidev.nav.total }}</span></div>
</div>

<!--
這是整體架構，從左到右。使用者在聊天視窗說話；管家後端包含 LLM、MCP 工具伺服器和計畫引擎，這是我們新做的；所有東西透過 oneM2M REST 寫進 OM2M 的 MN-CSE；Node-RED 負責橋接，並放虛擬的烤箱和冷氣；最右邊是 Arduino，接燈泡、伺服馬達和蜂鳴器，紅外線沿用 Lab 5。標籤顏色表示哪些沿用課堂實驗、哪些是新增。下面四層防護貫穿整條路徑：身分與 ACP、MCP 守門、裝置上限，以及稽核紀錄。
-->

---
layout: none
---

<div class="deck">
<div class="hd"><span class="no">8</span><span class="sec">高階示意圖 High-Level Illustration · 2/2</span><span class="grp">萬物聯網管家 · 第 9 組</span></div>
<div class="ttl">資料模型：oneM2M 資源樹與訊息負載</div>
<div class="bd">
<div class="row g16" style="height:100%">
<div class="col" style="width:430px">
<div class="h3">OM2M 服務層資源樹 (MN-CSE)</div>
<pre class="tree">MN-CSE
└─ <span class="n">Butler</span> <span class="c">(AE)</span>
   ├─ <span class="n">CMD</span>      <span class="c">下發指令容器 (cin 帶唯一遞增 id)</span>
   ├─ <span class="n">PLAN</span>     <span class="c">計畫持久化容器 (cin 存 JSON 計畫)</span>
   ├─ <span class="n">POLICY</span>   <span class="c">安全上限、ACP 角色、示範時鐘加速比</span>
   ├─ <span class="n">AUDIT</span>    <span class="c">誰 · 做什麼 · 時間戳 · 執行結果</span>
   ├─ <span class="n">light</span>    <span class="c">└ STATE (實體 LED 狀態 cin)</span>
   ├─ <span class="n">curtain</span>  <span class="c">└ STATE (實體伺服馬達角度 cin)</span>
   ├─ <span class="n">buzzer</span>   <span class="c">└ STATE (實體蜂鳴器狀態 cin)</span>
   ├─ <span class="n">oven</span>     <span class="c">└ STATE</span> <span class="a">(虛擬熱模型 cin)</span>
   └─ <span class="n">ac</span>       <span class="c">└ STATE</span> <span class="a">(虛擬空調溫度 cin)</span></pre>
</div>
<div class="col f1 g8">
<div class="h3">下發指令 Payload（由計畫引擎寫入 CMD）</div>
<pre class="code">{"id":17, "plan":"p-42", "dev":"ac", "do":"set",
 "params":{"temp":25}, "by":"operator"}</pre>
<div class="h3" style="margin-top:4px">硬體反饋 Payload（由邊緣節點回報至 STATE）</div>
<pre class="code">{"dev":"ac", "ack":17,
 "actual":{"power":"on","temp":25}, "ts":1731110400}</pre>
<div class="card soft" style="margin-top:4px"><div class="sm"><span class="b" style="color:#0284c7">冪等性與狀態一致性閉環：</span>遞增之指令編號 (<span class="mono">id</span>) 確保輪詢與重試具備冪等性，絕不重複誤動；<span class="mono">ack</span> 讓計畫引擎嚴密核對指令與真實硬體狀態；任一裝置之當前最新狀態，皆可透過其專屬 STATE 容器之最新 contentInstance (<span class="mono">la</span>) 獲取。</div></div>
</div>
</div>
</div>
<div class="ft"><span>物聯網技術與應用 · 期末專題提案 · 2026 秋</span><span>{{ $slidev.nav.currentPage }} / {{ $slidev.nav.total }}</span></div>
</div>

<!--
這頁是資料模型。左邊是 OM2M 裡的資源樹：Butler 這個 AE 底下有 CMD、PLAN、POLICY、AUDIT 四個容器，每個裝置各有一個 STATE 容器。右邊是兩種訊息：指令帶有編號，狀態會回報 ack，也就是它執行到哪一個指令。這樣有兩個好處：第一，輪詢時就算讀到同一筆指令也不會重複執行；第二，計畫引擎可以比對指令和實際狀態是否一致。
-->

---
layout: none
---

<div class="deck">
<div class="hd"><span class="no">9</span><span class="sec">可能的挑戰與解法 Potential Challenges and Solutions</span><span class="grp">萬物聯網管家 · 第 9 組</span></div>
<div class="ttl">可能的挑戰與工程解法 (Risk Matrix)</div>
<div class="bd">
<div class="tb"><div class="tr th" style="grid-template-columns:260px 1fr"><div class="td"><div>潛在工程挑戰與風險</div></div><div class="td"><div>對應之工程解決方案與備案設計</div></div></div>
<div class="tr" style="grid-template-columns:260px 1fr"><div class="td"><div><span class="b" style="color:#b45309">自然語言語意歧義</span> (「1/3」開或關)</div></div><div class="td"><div>嚴格 Schema 校驗；先反問澄清；下發硬體前輸出結構化摘要並要求二次確認</div></div></div>
<div class="tr" style="grid-template-columns:260px 1fr"><div class="td"><div><span class="b" style="color:#b45309">LLM 幻覺與越界輸出</span> (裝置或數值錯誤)</div></div><div class="td"><div>Tool Schema 列舉合法裝置與範圍；伺服器端強制限幅；執行前提供 Dry-run 預演確認</div></div></div>
<div class="tr" style="grid-template-columns:260px 1fr"><div class="td"><div><span class="b" style="color:#0284c7">網路傳輸抖動 Jitter</span> (Wi-Fi 輪詢延遲)</div></div><div class="td"><div>由計畫引擎本機嚴格計時下發；實測記錄抖動；必要時將步驟陣列下發由 Arduino 本地調度</div></div></div>
<div class="tr" style="grid-template-columns:260px 1fr"><div class="td"><div><span class="b" style="color:#0284c7">指令遺失或重複下發</span> (輪詢式架構)</div></div><div class="td"><div>全系統採用單調遞增指令編號 (<span class="mono">id</span>)、STATE 容器 <span class="mono">ack</span> 機制，搭配 Node-RED 隊列保證冪等</div></div></div>
<div class="tr" style="grid-template-columns:260px 1fr"><div class="td"><div><span class="b" style="color:#be123c">高功率加熱裝置安全</span> (烤箱過熱風險)</div></div><div class="td"><div>採用軟體一階熱模型模擬；雙重軟體限溫 (≤ 250°C)、強制二次確認與 120min 超時強制熔斷</div></div></div>
<div class="tr" style="grid-template-columns:260px 1fr"><div class="td"><div><span class="b">舊版 OM2M 相容性</span> (ACP 行為未知)</div></div><div class="td"><div>第 1 週先期驗證 (Spike)；XML <span class="mono">con</span> 放 JSON 字串；若 CSE ACP 不足，由工具伺服器主動承擔角色檢查</div></div></div>
<div class="tr" style="grid-template-columns:260px 1fr"><div class="td"><div><span class="b">課堂展示時間限制</span> (真實 70 分鐘耗時)</div></div><div class="td"><div>於 POLICY 內置加速時鐘 (×60，70 分鐘縮短至約 70 秒播畢)；預先錄製完整備援展示影片</div></div></div>
<div class="tr" style="grid-template-columns:260px 1fr"><div class="td"><div><span class="b">展示現場網路與 LLM 額度</span></div></div><div class="td"><div>群組 VM 採固定 IP 並實地聯調；配備規則式備援解析器 (Fallback)；設定第二組備用 API 金鑰</div></div></div>
</div>
</div>
<div class="ft"><span>物聯網技術與應用 · 期末專題提案 · 2026 秋</span><span>{{ $slidev.nav.currentPage }} / {{ $slidev.nav.total }}</span></div>
</div>

<!--
接著是可能遇到的挑戰和解法，共八項。語句歧義，靠澄清問題和執行前確認。LLM 出錯，靠工具綱要和伺服器端驗證。Wi-Fi 輪詢造成時間抖動，由計畫引擎掌握時鐘並實測延遲。指令遺失或重複，用編號和 ack。烤箱安全，用虛擬裝置加上上限、確認和自動關閉。舊版平台的風險，第一週就先做驗證。示範要等一小時的問題，用時間加速解決。最後是教室網路和 LLM 額度，我們準備了備案。
-->

---
layout: none
---

<div class="deck">
<div class="hd"><span class="no">10</span><span class="sec">工作與時程 Tasks and Schedule</span><span class="grp">萬物聯網管家 · 第 9 組</span></div>
<div class="ttl">工作甘特圖：六週時程與關鍵里程碑</div>
<div class="bd">
<div class="gt">
<div class="gh" style="grid-row:1;grid-column:1">核心工程項目 · 負責人</div>
<div class="gh" style="grid-row:1;grid-column:2"><span>第 1 週</span><span style="font-weight:500;font-size:10.5px">11/9–11/15</span></div>
<div class="gh" style="grid-row:1;grid-column:3"><span>第 2 週</span><span style="font-weight:500;font-size:10.5px">11/16–11/22</span></div>
<div class="gh" style="grid-row:1;grid-column:4"><span>第 3 週</span><span style="font-weight:500;font-size:10.5px">11/23–11/29</span></div>
<div class="gh" style="grid-row:1;grid-column:5"><span>第 4 週</span><span style="font-weight:500;font-size:10.5px">11/30–12/6</span></div>
<div class="gh" style="grid-row:1;grid-column:6"><span>第 5 週</span><span style="font-weight:500;font-size:10.5px">12/7–12/13</span></div>
<div class="gh" style="grid-row:1;grid-column:7"><span>第 6 週</span><span style="font-weight:500;font-size:10.5px">12/14–12/20</span></div>

<div class="gl" style="grid-row:2;grid-column:1"><span>1. 系統架構與 oneM2M 資源樹設計</span><span class="own">全員</span></div>
<div class="gc" style="grid-row:2;grid-column:2"></div><div class="gc" style="grid-row:2;grid-column:3"></div><div class="gc" style="grid-row:2;grid-column:4"></div><div class="gc" style="grid-row:2;grid-column:5"></div><div class="gc" style="grid-row:2;grid-column:6"></div><div class="gc" style="grid-row:2;grid-column:7"></div>
<div class="gb X" style="grid-row:2;grid-column:2 / 3">架構定案</div>

<div class="gl" style="grid-row:3;grid-column:1"><span>2. Arduino 邊緣韌體與 Node-RED 閘道隊列</span><span class="own">A·B</span></div>
<div class="gc" style="grid-row:3;grid-column:2"></div><div class="gc" style="grid-row:3;grid-column:3"></div><div class="gc" style="grid-row:3;grid-column:4"></div><div class="gc" style="grid-row:3;grid-column:5"></div><div class="gc" style="grid-row:3;grid-column:6"></div><div class="gc" style="grid-row:3;grid-column:7"></div>
<div class="gb A" style="grid-row:3;grid-column:2 / 5">實體硬體致動鏈</div>

<div class="gl" style="grid-row:4;grid-column:1"><span>3. MCP 工具伺服器、計畫引擎與 LLM 整合</span><span class="own">C</span></div>
<div class="gc" style="grid-row:4;grid-column:2"></div><div class="gc" style="grid-row:4;grid-column:3"></div><div class="gc" style="grid-row:4;grid-column:4"></div><div class="gc" style="grid-row:4;grid-column:5"></div><div class="gc" style="grid-row:4;grid-column:6"></div><div class="gc" style="grid-row:4;grid-column:7"></div>
<div class="gb C" style="grid-row:4;grid-column:3 / 6">時序排程引擎與對話終端</div>

<div class="gl" style="grid-row:5;grid-column:1"><span>4. 虛擬熱模型 (冷氣/烤箱) 與安全防護網</span><span class="own">A·C</span></div>
<div class="gc" style="grid-row:5;grid-column:2"></div><div class="gc" style="grid-row:5;grid-column:3"></div><div class="gc" style="grid-row:5;grid-column:4"></div><div class="gc" style="grid-row:5;grid-column:5"></div><div class="gc" style="grid-row:5;grid-column:6"></div><div class="gc" style="grid-row:5;grid-column:7"></div>
<div class="gb B" style="grid-row:5;grid-column:4 / 7">上限裁切 · 熔斷 · ACP 權限</div>

<div class="gl" style="grid-row:6;grid-column:1"><span>5. 系統全鏈路整合、精度評估與發表準備</span><span class="own">全員</span></div>
<div class="gc" style="grid-row:6;grid-column:2"></div><div class="gc" style="grid-row:6;grid-column:3"></div><div class="gc" style="grid-row:6;grid-column:4"></div><div class="gc" style="grid-row:6;grid-column:5"></div><div class="gc" style="grid-row:6;grid-column:6"></div><div class="gc" style="grid-row:6;grid-column:7"></div>
<div class="gb X" style="grid-row:6;grid-column:5 / 8">端到端量測 · 影片備案 · 成果展示</div>

<div class="gl" style="grid-row:7;grid-column:1;background:#fff1f2"><span class="b" style="color:#e11d48">關鍵里程碑</span></div>
<div class="ms" style="grid-row:7;grid-column:2"></div>
<div class="ms" style="grid-row:7;grid-column:3">◆ M1<br/><span style="font-size:10px;font-weight:400">對話控制燈泡</span></div>
<div class="ms" style="grid-row:7;grid-column:4"></div>
<div class="ms" style="grid-row:7;grid-column:5">◆ M2<br/><span style="font-size:10px;font-weight:400">雙裝置時序調度</span></div>
<div class="ms" style="grid-row:7;grid-column:6">◆ M3<br/><span style="font-size:10px;font-weight:400">五裝置安全聯動</span></div>
<div class="ms" style="grid-row:7;grid-column:7">◆ M4<br/><span style="font-size:10px;font-weight:400">期末現場成果展示</span></div>
</div>

<div class="row g16" style="margin-top:16px;align-items:center">
<span class="tag t b" style="padding:4px 10px"><span style="color:#0284c7">● 組員 A</span> OM2M / Node-RED 閘道</span>
<span class="tag a b" style="padding:4px 10px"><span style="color:#d97706">● 組員 B</span> Arduino 硬體韌體</span>
<span class="tag v b" style="padding:4px 10px"><span style="color:#7c3aed">● 組員 C</span> 後端核心 / LLM 整合</span>
<span class="tag g b" style="padding:4px 10px"><span style="color:#059669">● 全員</span> 系統架構 / 整合測試</span>
</div>
</div>
<div class="ft"><span>物聯網技術與應用 · 期末專題提案 · 2026 秋</span><span>{{ $slidev.nav.currentPage }} / {{ $slidev.nav.total }}</span></div>
</div>

<!--
這是甘特圖，我們規劃六週。第一週做架構與資源樹設計。第二到第四週完成實體硬體與 Node-RED 閘道致動鏈。第三到第五週完成 MCP 工具伺服器、計畫引擎與 LLM 整合。第四到第六週完成虛擬熱模型與安全防護網。最後兩週全員進行整合量測、備案影片錄製與期末發表。四個里程碑依序推進：M1 對話控制燈泡，M2 雙裝置時序調度，M3 五裝置安全聯動，M4 期末完整成果展示。
-->

---
layout: none
---

<div class="deck">
<div class="hd"><span class="no plus">+</span><span class="sec">補充 Supplement · 展示與評估 Demo and Evaluation</span><span class="grp">萬物聯網管家 · 第 9 組</span></div>
<div class="ttl">補充：展示劇本與量化評估指標</div>
<div class="bd big">
<div class="row g16" style="align-items:flex-start">
<div class="card bar f1"><div class="h3"><span class="tag t">展示</span> 5 分鐘現場即時展示劇本</div>
<div class="st"><div class="stn">1</div><div class="stt">自然語言一口氣下達 5 裝置複合指令；管家輸出結構化摘要並二次確認。</div></div>
<div class="st"><div class="stn">2</div><div class="stt">時序圖面板與 OM2M 資源樹即時反映步驟（啟用 ×60 示範時鐘加速）。</div></div>
<div class="st"><div class="stn">3</div><div class="stt">執行中途插單動態變更：「冷氣改 24 度」、「取消燈泡後續排程」。</div></div>
<div class="st"><div class="stn">4</div><div class="stt">惡意/越界測試：故意輸入烤箱 300 度及 viewer 越權操作，全數被攔截。</div></div>
<div class="st"><div class="stn">5</div><div class="stt">調出 AUDIT 容器：展示從對話請求到硬體反饋之完整不可篡改審計鏈。</div></div></div>
<div class="card bar a f1"><div class="h3 a"><span class="tag a">指標</span> 五大客觀量化評估維度</div>
<div class="li a"><span class="b" style="color:#0f172a">端到端致動延遲 (Latency)</span>：從送出對話至首個硬體動作的中位數與 P99。</div>
<div class="li a"><span class="b" style="color:#0f172a">時序排程誤差 (Jitter)</span>：各排程步驟與真實執行時間的毫秒級誤差分布。</div>
<div class="li a"><span class="b" style="color:#0f172a">意圖轉譯精準度 (Accuracy)</span>：30 句以上複合測試句的 Tool-calling 準確率。</div>
<div class="li a"><span class="b" style="color:#0f172a">安全防護攔截率 (Guard Interception)</span>：越界參數與越權指令的 100% 阻斷驗證。</div>
<div class="li a"><span class="b" style="color:#0f172a">提示詞注入抗性 (Prompt-Injection)</span>：惡意設備名稱不得誘發非預期致動。</div>
<div class="card soft a" style="margin-top:10px"><div class="sm"><span class="b" style="color:#b45309">備案準備：</span>已預先錄製各環節 HD 演示影片，並備妥本機規則式解析器，抵禦現場網路斷線風險。</div></div></div>
</div>
</div>
<div class="ft"><span>物聯網技術與應用 · 期末專題提案 · 2026 秋</span><span>{{ $slidev.nav.currentPage }} / {{ $slidev.nav.total }}</span></div>
</div>

<!--
最後補充我們預計的展示和評估。展示大約五分鐘：一句話控制五個裝置，看時間軸和資源樹即時更新，中途修改或取消，故意送出不安全或沒有權限的請求，最後打開稽核紀錄。評估的指標包括：端到端延遲、時間誤差、自然語言轉計畫的正確率、防護機制的攔截率，還有提示注入測試。另外也準備了錄影和規則式解析器當備案。
-->

---
layout: none
---

<div class="deck">
<div class="hd"><span class="no">11</span><span class="sec">參考資料 References</span><span class="grp">萬物聯網管家 · 第 9 組</span></div>
<div class="ttl">參考文獻與國際標準規範</div>
<div class="bd">
<div style="columns:2;column-gap:28px;font-size:13px;line-height:1.55">
<div style="margin-bottom:9px;break-inside:avoid"><span class="b" style="color:#0284c7">[1]</span> oneM2M TR-0001, “Use Cases Collection,” oneM2M.（簡報範本與標準使用案例規範）</div>
<div style="margin-bottom:9px;break-inside:avoid"><span class="b" style="color:#0284c7">[2]</span> oneM2M TS-0001, “Functional Architecture,” oneM2M.（服務層功能架構標準）</div>
<div style="margin-bottom:9px;break-inside:avoid"><span class="b" style="color:#0284c7">[3]</span> oneM2M TR-0081, “MCP to oneM2M interworking (architecture and security).” specifications.onem2m.org/tr/tr-0081</div>
<div style="margin-bottom:9px;break-inside:avoid"><span class="b" style="color:#0284c7">[4]</span> oneM2M WI-0122, “oneM2M and Model Context Protocol.” specifications.onem2m.org/wi/wi-0122</div>
<div style="margin-bottom:9px;break-inside:avoid"><span class="b" style="color:#0284c7">[5]</span> onem2m-mcp v0.4.1, “AI agents for the oneM2M IoT service layer,” PyPI, Aug 2026. pypi.org/project/onem2m-mcp</div>
<div style="margin-bottom:9px;break-inside:avoid"><span class="b" style="color:#0284c7">[6]</span> “IoT-MCP: Bridging LLMs and IoT Systems Through Model Context Protocol,” arXiv:2510.01260.</div>
<div style="margin-bottom:9px;break-inside:avoid"><span class="b" style="color:#0284c7">[7]</span> Model Context Protocol Specification. modelcontextprotocol.io</div>
<div style="margin-bottom:9px;break-inside:avoid"><span class="b" style="color:#0284c7">[8]</span> E. King, H. Yu, S. Lee, C. Julien, “Sasha: Creative Goal-Oriented Reasoning in Smart Homes with Large Language Models,” Proc. ACM IMWUT, 2024.</div>
<div style="margin-bottom:9px;break-inside:avoid"><span class="b" style="color:#0284c7">[9]</span> Eclipse OM2M, open-source oneM2M service platform. eclipse.dev/om2m</div>
<div style="margin-bottom:9px;break-inside:avoid"><span class="b" style="color:#0284c7">[10]</span> Node-RED, flow-based programming for the Internet of Things. nodered.org</div>
<div style="margin-bottom:9px;break-inside:avoid"><span class="b" style="color:#0284c7">[11]</span> Arduino Uno WiFi Rev2, WiFiNINA and hardware documentation. docs.arduino.cc</div>
<div style="margin-bottom:9px;break-inside:avoid"><span class="b" style="color:#0284c7">[12]</span> Home Assistant, open-source home automation. home-assistant.io</div>
<div style="margin-bottom:9px;break-inside:avoid"><span class="b" style="color:#0284c7">[13]</span> Lab 4、Lab 5 講義，物聯網技術與應用 (IoT Technologies and Applications)，2026 秋。</div>
</div>
</div>
<div class="ft"><span>物聯網技術與應用 · 期末專題提案 · 2026 秋</span><span>{{ $slidev.nav.currentPage }} / {{ $slidev.nav.total }}</span></div>
</div>

<!--
最後是參考資料。前面四項是 oneM2M 標準與 MCP 相關的工作項目，第五到第八項是相近的開源與研究成果，後面是我們使用的工具與平台，最後是課堂的 Lab 講義。以上是我們第九組的報告，謝謝大家，歡迎提問。
-->
