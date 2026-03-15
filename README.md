# Dynamic Novel
**The Next-Generation Markdown Engine for Dynamic Fiction Novel.**
Dynamic Novel (DN) 是一個開源的內容開發框架，旨在將傳統的文本小說轉化為包含動畫、影片和互動環節的網上小說寫作框架。DN 讓創作者只需編寫 Markdown，即可驅動 AI 生成高品質的影片、音訊與工業級一致性的視覺資產。

## 🌟 核心理念：文字即電影 (Text-as-Cinema)
在 OVN 框架中，小說不再是靜態的文字，而是一個動態的執行環境：
語義觸發 (Semantic Triggers)：文字段落直接與 OMP 影片和 OSP 音軌聯動。
身分注入 (Identity Injection)：讀者可定義主角 DNA，全書視覺自動同步。
預測性渲染 (Predictive Rendering)：在讀者閱讀當前段落時，後台預先渲染下一幕 AI 影片。
邏輯分支 (Branching Logic)：在 Markdown 中直接編寫劇情分支與變數控制。

## 📂 專案結構 (Project Structure)
```text
/my-dynamic-novel
├── config.ovn.yaml        # 全域設定 (AI Engine, 解析度, 渲染優先級)
├── /protocols             # 引用 OpenWorldProtocol 規範
│   ├── identity.oisx      # 定義角色 (如：企鵝將軍) 的視覺一致性
│   └── orchestra.osp      # 定義音樂風格與樂器
├── /chapters              # 動態小說內容
│   ├── chapter-1.md       # 結合文字、影片與邏輯標籤
│   └── chapter-2.md
└── /public                # 緩存的生成資產
```

📝 寫作語法範例 (Writing Syntax)
使用 OVN 擴展的 Markdown 語法，輕鬆嵌入協議指令：
markdown
---
title: "企鵝帝國的授權"
audio_base: "@Imperial_Gong_Ambient"
---

# 第一章：冰川王座

人類將軍 @Human_General 單膝跪地，沉重的盔甲在冰面上摩擦。

::video{src="OMP.Scene_01_Kneel" parallax="true"}

「將軍，」企鵝皇帝 @Emperor_Penguin 緩緩開口，「你將成為朕在陸地上的利劍。」

> **[EVENT: if $loyalty > 50 play OSP.Fanfare_Success else play OSP.Suspense_Low]**

[[ 接受玉璽 ]] -> set $loyalty += 10 -> load ch2_servant.md
[[ 猶豫不決 ]] -> set $loyalty -= 5  -> load ch2_revolt.md
請謹慎使用程式碼。

## 🛠️ 技術組件 (Tech Stack)
* OVN-Renderer: 基於 Next.js 的高性能即時渲染前端。
* Remark-OVN: 自定義 Markdown 解析器，識別 OWP 協議標籤。
* Bridge-API: 連結 OpenAI Sora, Runway, Udio 等 AI 引擎的統一接口。
* Identity-Cache: 確保跨章節角色一致性的 Embedding 管理器。

## 🚀 快速開始 (Quick Start)
1. 安裝 CLI
```bash
npm install -g @openworld/ovn-cli
```

2. 初始化專案
```bash
ovn init my-novel
```

3. 本地預覽 (開啟預測渲染)
```bash
ovn dev
```

## 🤝 貢獻與生態 (Ecosystem)
我們正在建立一個「現實原始碼」的生態系：
* OMP (Visuals): 影片分鏡協議。
* OISx (Images): 精確圖片控制。
* OSP (Audio): 聽覺定義協議。
* OIS (Industrial): 工業邏輯定義。

## 📜 授權 (License)
本專案採用 MIT License。
"Stop writing books. Start building worlds."
