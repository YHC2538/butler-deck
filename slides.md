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
<div class="cv-m">物聯網技術與應用 (IoT Technologies and Applications) · 2026 年秋季<br/>組員與報告分工：徐瑞利 (問題與背景) · 陳羿豪 (場景與流程) · 孫悅騫 (架構與時程)</div>
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
【負責人】：徐瑞利
【預估時間】：30 秒 (累計 0:00 - 0:30)
【講解要點與講稿】：
各位評審老師、助教、同學們好，我們是第九組，成員有徐瑞利、陳羿豪與孫悅騫。今天我們要報告的物聯網專案題目是「萬物聯網管家 (Butler of Everything)」。簡單來說，我們的目標是讓使用者在家中只需說一句自然語言指令，智慧管家就能自動理解意圖、拆解成具有時間順序的執行計畫，並透過 oneM2M 國際標準通訊協定，安全、協調地調度家中多個跨協定裝置。接下來我們將從問題痛點開始為大家做完整介紹。
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
【負責人】：徐瑞利
【預估時間】：45 秒 (累計 0:30 - 1:15)
【講解要點與講稿】：
首先看到背景與痛點。現今的智慧家庭普遍面臨三大瓶頸：第一，各裝置被困在各自獨立的 App 孤島中；第二，排程需要手動逐一手動設定，若遇到複合需求（如「現在開除濕23度，半小時後改25度並關閉」）設定極其繁瑣；第三，缺乏動態適應力與跨協定互通標準。我們的核心構想是在使用者與裝置之間建立「智慧管家」：前端由大語言模型（LLM）將自然語言轉化為帶有時間軸的結構化計畫（Plan），後端透過 oneM2M 統一架構逐步調度裝置並即時回饋狀態。我們結合課堂 Lab 4 的 OM2M 架構與 Lab 5 的 Node-RED 及 Arduino 實體硬體，兼顧智慧便利與架構標準化。
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
【負責人】：徐瑞利
【預估時間】：45 秒 (累計 1:15 - 2:00)
【講解要點與講稿】：
這一頁展示管家的五大核心功能模組。最核心的是「語言轉排程」：LLM 只負責單次把模糊語意精準轉換為具備時間戳記的結構化步驟，後續排程完全由排程器自主推進，不重複消耗 LLM 費用；第二是「狀態回饋」，感測器數據即時回傳同步；第三是「計畫生命週期管理」，支援中途查詢、動態修改或取消；第四是「安全與存取控制」，所有指令必須通過 ACP 白名單審查，高危險設備更有防呆機制。右側的真實情境展示了管家如何在一段話中同時排程除濕機、烤箱、冷氣與定時回饋。
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
【負責人】：徐瑞利
【預估時間】：30 秒 (累計 2:00 - 2:30)
【講解要點與講稿】：
接下來是相關研究分析，我們將現有文獻與產品依距離區分為遠、中、近三層。遠距研究是市售商用智慧助理，如 Amazon Alexa、Google Home 與 Apple Home。雖然它們語音互動成熟且市佔率高，但本質上皆為封閉私有生態系，不支援開放的 oneM2M 資源架構，且自動化排程多半仰賴手動點擊或固定 Routine，缺乏即時修正結構化時間軸的能力，權限機制也無法由使用者完全自訂掌控。
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
【負責人】：徐瑞利
【預估時間】：35 秒 (累計 2:30 - 3:05)
【講解要點與講稿】：
中距研究是學術界結合 LLM 與智慧家庭的探索，例如 Sasha (2024)、Home Assistant 的 LLM Conversation Agent 以及 IoT-MCP。這些研究成功驗證了「LLM 呼叫裝置工具」的可行性；然而，它們大多停留在單次即時呼叫，缺乏多步驟的「時間延遲排程」，也沒有建立在國際物聯網標準 oneM2M 之上，更缺乏實體硬體防呆白名單與計畫生命週期管理的完整機制。
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
【負責人】：徐瑞利
【預估時間】：35 秒 (累計 3:05 - 3:40)
【講解要點與講稿】：
近距研究則是 oneM2M 官方近期發布的 TR-0081 與 WI-0122 規範，以及開源的 onem2m-mcp 工具。標準組織也正朝向 MCP 與 oneM2M 整合邁進。但我們進一步突破的地方在於：現有開源實作主要針對 ACME CSE，對 OM2M 支援有限，且僅支援單次資源查詢；而我們專案在此基礎上完整實作了「帶時間軸的多步計畫排程」、實體硬體狀態同步、安全性白名單攔截與稽核軌跡。
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
【負責人】：徐瑞利
【預估時間】：40 秒 (累計 3:40 - 4:20)
【講解要點與講稿】：
這一頁是我們與各類現有方案的綜合比較。萬物聯網管家的三大不可取代優勢為：第一，純粹的 oneM2M 開放標準資源模型，杜絕廠商綁定；第二，狀態化計畫模型，計畫可存儲、查詢、暫停或取消，並具備回滾容錯能力；第三，多層級的安全白名單與即時稽核機制。
【交接提示】：接下來，我把發言棒交給陳羿豪，由他為大家深入說明 TR-0001 規範下的參與者、前置條件，以及系統的正常與替代流程。
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
【負責人】：陳羿豪  
【預估時間】：35 秒 (累計 04:20 - 04:55)  
【講解要點與講稿】：  
接著我用最直覺的方式，帶大家看管家是怎麼運作的。  
首先看系統裡的幾位主角 (總共四個)：第一位是「使用者」，也就是出嘴下指令的我們；  
第二位是「管家大腦」，也就是 LLM，負責聽懂人話，並排出時間行程表；第三位就是「家電夥伴」，包含我們桌上實體的 Arduino——控制燈泡、窗簾馬達與蜂鳴器，以及電腦裡模擬的烤箱跟冷氣。中間我們透過課堂學過的 OM2M 與 Node-RED 把大家串在一起。角色分工非常清晰！
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
【負責人】：陳羿豪  
【預估時間】：35 秒 (累計 04:55 - 05:30)  
【講解要點與講稿】：  
再來是前置條件，也就是管家上工前要確認的三件事：  
第一，「連線準備好了」：Arduino 連上 Wi-Fi，中介軟體和資料庫也都開好在線等候。  
第二，「安全守則訂好了」：每台家電有明確的使用權限，不能隨便亂動危險設備。  
第三，「示範加速器」：因為有些排程可能長達一小時，我們在環境中設定了「時間加速」，等下 Demo 時只要幾分鐘就能呈現成果，總不能讓大家在台下乾等我們 1hr 吧。
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
【負責人】：陳羿豪  
【預估時間】：30 秒 (累計 05:30 - 06:00)  
【講解要點與講稿】：  
那什麼時候會叫醒管家做事呢？主要有三種情況：  
第一種最直接，就是「主人開口」說話或傳文字指令；  
第二種是「時間到了」，例如十分鐘後該調溫度、一小時後該關燈，計時器會自動叫醒它；  
第三種是「狀態改變」，像是烤箱感測器發現溫度到了，主動叫蜂鳴器響，或者設備開太久超時，系統為了安全自動關掉。當然，如果主人臨時想改或想取消，管家也會隨時響應。  
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
【負責人】：陳羿豪  
【預估時間】：45 秒 (累計 06:00 - 06:45)  
【講解要點與講稿】：  
接下來是核心的運作流程。這張圖看起來步驟很多，但大家只要記住管家做事的四個節奏：  
1.「聽懂排程」：AI 一聽懂你的話，立刻排出一張清楚的時間清單 (就是甚麼時間該做甚麼事情)。  
2.「安全檢查」：管家先檢查這幾台設備能不能動；遇到像烤箱這種高溫家電，會主動向你再確認一次。  
3.「照表操課」：確認沒問題就存進系統，時間一到，排程器自動送出動作給 Arduino 執行。  
4.「回報記錄」：硬體做完立刻回傳狀態，管家記下日誌並通知主人。
這裡最厲害的是：AI 只在最一開始動腦排程一次，後面全部由排程器精確執行，既省算力又保證絕不出錯！
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
【負責人】：陳羿豪  
【預估時間】：45 秒 (累計 06:45 - 07:30)  
【講解要點與講稿】：  
我們來看這張時間軸，實際感受一下！  
假設你出門前說了一句：「窗簾開三分之一、烤箱預熱 200 度，冷氣開十分鐘後轉 25 度，一小時後全關」：  
一開始在時間 0，窗簾馬達立刻轉到三分之一，烤箱開始加熱，冷氣也啟動；  
到了第十分鐘，冷氣自動從 23 度微調到 25 度更省電；  
當烤箱達到 200 度時，蜂鳴器立刻嗶嗶叫通知你；  
到了五十分鐘，烤箱先自動斷電；七十分鐘時，全家設備通通安全關閉。  
你只要講一句話，接下來的一小時管家全幫你照顧好！
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
【負責人】：陳羿豪  
【預估時間】：40 秒 (累計 07:30 - 08:10)  
【講解要點與講稿】：  
那萬一遇到突發狀況怎麼辦？我們準備了很周全的應對：  
如果話沒說清楚，比如「窗簾三分之一」到底要開還是關，管家會反問一句確認；  
如果指令太離譜，像是「烤箱開 500 度」，系統會自動限制在安全上限並提醒你；  
如果有人想操控沒授權的設備，管家會直接拒絕並記下警告；  
萬一遇到網路不穩，系統會自動重試兩次；要是你中途突然反悔想改，管家也能隨時取消舊計畫、換成新的。  
【交接提示】：接下來請孫悅騫為我們解說系統架構與實作規劃！
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
【負責人】：孫悅騫
【預估時間】：50 秒 (累計 08:10 - 09:00)
【講解要點與講稿】：
謝謝羿豪。大家好，我是孫悅騫，接下來由我為大家解說高階系統架構與實作規劃。如圖所示，整個架構分為三層：最上層是使用者互動介面；中間是智慧核心層，包含管家代理 (LLM)、MCP 工具集以及計畫排程器，負責意圖解析與計時調度；底層是 oneM2M 基礎設施層。我們完整繼承並擴充了課堂實驗：透過 OM2M IN-CSE/MN-CSE 提供標準資源管理 (Lab 4)，透過 Node-RED 扮演中介軟體網關，並以 Arduino 實作客廳燈、除濕機馬達、警示蜂鳴器等實體硬體 (Lab 5)。中間透過 oneM2M 訂閱與通知機制實現完全解耦。
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
【負責人】：孫悅騫
【預估時間】：45 秒 (累計 09:00 - 09:45)
【講解要點與講稿】：
這一頁展示 oneM2M 標準資源樹模型。在 OM2M 的 MN-CSE 與 IN-CSE 下，我們建立了專屬的 Butler AE。其下包含四大核心容器：CMD 用於非同步指令派送、PLAN 用於存儲完整計畫生命週期、POLICY 存放安全存取權限、AUDIT 記錄所有操作稽核日誌。而在各設備節點下，則設有 STATE 容器反映硬體即時狀態。透過 ContentInstance (cin) 的寫入與訂閱觸發，任何時間點都能精確追溯「誰在何時下達了何種指令、硬體當前真實狀態為何」，確保系統透明與可審計性。
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
【負責人】：孫悅騫
【預估時間】：40 秒 (累計 09:45 - 10:25)
【講解要點與講稿】：
第 9 部分是我們預見的工程挑戰與具體解法：第一，自然語言歧義透過反問澄清與結構化確認化解；第二，LLM 幻覺透過 MCP Schema 強制檢查與設備屬性白名單完全隔絕；第三，實體網路延遲與封包遺失，透過指令序號與 ACK 確認機制進行重試；第四，實體安全風險，透過看門狗定時器強制關閉超時設備；第五，展示時間受限問題，我們內建了可動態調整的時間加速倍率，讓長週期排程在評審面前流暢演示。
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
【負責人】：孫悅騫
【預估時間】：40 秒 (累計 10:25 - 11:05)
【講解要點與講稿】：
第 10 部分是六週的實作甘特圖與里程碑規劃。W1 完成架構定義與資源樹設計；W2 至 W4 完成 Arduino 實體硬體與 Node-RED 雙向驅動；W3 至 W5 整合 MCP 工具集、計畫排程器與 LLM；W4 至 W5 完善安全白名單與例外流程；W6 進行端到端全系統聯調與展示彩排。四大里程碑分別為：M1 基礎通訊建立、M2 狀態雙向同步、M3 計畫自主推進，以及 M4 期末成果展示就緒。
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
【負責人】：孫悅騫
【預估時間】：40 秒 (累計 11:05 - 11:45)
【講解要點與講稿】：
補充說明我們的期末展示劇本與量化驗證指標。展示當天我們將演示一條真實複合指令，即時連動 5 個實體與模擬設備，並在排程中示範動態修改計畫，最後刻意注入一筆未授權指令，展示安全白名單的即時阻擋與 Audit 紀錄。量化驗證指標包含：語意解析延遲小於 3 秒、排程計時誤差小於 1 秒、狀態同步延遲小於 500 毫秒、指令解析正確率大於 95%、計畫中斷衝突率 0%，確保專案具備扎實的工程水準。
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
【負責人】：孫悅騫
【預估時間】：25 秒 (累計 11:45 - 12:10)
【講解要點與講稿】：
最後是本專案引用的標準文獻與參考資料，涵蓋 oneM2M TS-0001、TR-0081 等官方規範、Anthropic MCP 協議、相關學術論文以及本堂課的實驗講義。以上是我們第九組的期末專題提案報告，感謝簡教授與大家的聆聽，現在開放大家提問與指教，謝謝！
-->
