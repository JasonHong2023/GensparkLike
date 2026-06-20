## Context

GensparkLike 是一個以 Genspark.ai 為設計參考的展示專案。目前已完成首頁（技能交換平台），現在需要新增一個與 genspark.ai/zh-tw 版面結構 1:1 相同的「Genspark AI 工作空間 4.0」頁面，從首頁「開始探索」按鈕進入。

This project needs a new workspace landing page that visually mirrors genspark.ai/zh-tw, accessible from the homepage's "Start Exploring" button.

### 現狀 / Current State

- 首頁 `index.html` 已建立，內容為 Skill Exchange Platform
- CSS 設計系統在 `assets/css/style.css`（包含 Inter / Source Serif 4 / JetBrains Mono 字體、#000/#FFF/#0F7FFF 色系、玻璃效果）
- Navbar 目前顯示：功能 / 分類 / 流程

### 限制 / Constraints

- 純靜態 HTML + CSS + JS（無框架）
- 所有功能按鈕與連結皆為 `#` placeholder
- 雙語註解：繁體中文 + English
- 同一份 `style.css`（追加 workspace 專用區段）

## Goals / Non-Goals

**Goals:**
- 建立 `workspace/index.html` 頁面，版面結構 1:1 複製 genspark.ai/zh-tw
- 修改首頁 Navbar 為 genspark.ai 導航結構
- 首頁「開始探索」按鈕連結到 `workspace/`
- 所有互動元件暫為展示用 placeholder

**Non-Goals:**
- 任何後端功能、登入、資料儲存
- 實際的 AI 操作或技能執行
- 子頁面路由（點擊 Nav 項目不跳轉）
- 語言切換的實際邏輯

## Decisions

| Decision | Choice | Rationale |
|---|---|---|
| 新頁面路徑 | `workspace/index.html` | 使用者指定 `workspace/` |
| Navbar 改造 | 改為 genspark.ai 結構 | 使用者指定要與目標一致 |
| CSS 管理 | 追加至現有 `style.css` | 使用者指定同一份 CSS |
| Hero 宣傳圖 | CSS 灰色佔位區塊 | 無法取得 Genspark 原圖 |
| 工具目錄 | 靜態 HTML 列表 | 純展示，無過濾/搜尋功能 |
| 定價卡 | `#` placeholder CTA | 不上線真正金流 |
| 語言選擇器 | 靜態語言列表 | 無實際切換邏輯 |

## Page Structure

```
workspace/index.html
──────────────────────────────────────────────────────────

NAVBAR (glassmorphism, fixed top)
├── Logo: GensparkLike
├── 首頁 (links to /)
├── 技能 (#)
├── 工作流程 (#)
├── 雲端硬碟 (#)
├── 更多 (#) + New badge
└── [placeholder CTA button]

HERO (左右雙欄, dark gradient background)
├── 左欄
│   ├── Badge: GensparkLike AI 工作空間 4.0
│   ├── H1: 幾分鐘即可建立自訂儀表板、CRM 和系統
│   ├── P: 一個 AI 代理，將來自收件匣、檔案、應用程式和資料庫的資料...
│   ├── 上線優惠截止至 7月2日
│   ├── 定價卡 3 欄 (個人5折·2週 / Team5折·4週 / 企業免費·4週)
│   └── CTAs: [試用 AgentBase] [暫時不要]
└── 右欄
    └── 產品宣傳圖 placeholder (灰色區塊, responsive)

PRODUCTS SECTION (section-light)
├── Section label: ✦ Products / 產品
├── H2: 認識我們的產品 / Our Products
└── Product grid (4 cards)
    ├── Genspark Claw — 原生桌面端 AI 客戶端...
    ├── Speakly — 即時翻譯與 AI 會議記錄...
    ├── GenClipboard — 智慧剪貼簿...
    └── GenTerminal — AI 終端機...

TOOLS SECTION (section-dark)
├── Section label: ✦ Tools / 工具
├── H2: 探索 AI 工具 / Explore AI Tools
└── Tools grid (4 columns of categories)
    ├── 商務與效率 (19 items)
    ├── 寫作與內容 (9 items)
    ├── 設計與視覺 (16 items)
    └── 音訊與影片 (6 items)

FOOTER
├── Multi-column grid
│   ├── Brand column: Logo + 簡述
│   ├── Products column
│   ├── Tools column (compressed to 2 sub-cols)
│   ├── About column
│   └── Download column (App Store + Google Play badges)
├── Social icons (X / LinkedIn / Instagram / Discord / YouTube / TikTok)
├── Language selector (19 languages dropdown)
└── Bottom bar: © 2026 GensparkLike Inc.

index.html 修改
──────────────────
- Navbar: Logo | 首頁(/)| 技能(#)| 工作流程(#)| 雲端硬碟(#)| 更多(#)
- [開始探索] href → "workspace/"

CSS 追加 (style.css 底部)
─────────────────────────
.workspace-nav { ... }
.workspace-hero { ... }
.pricing-cards { ... }
.pricing-card { ... }
.product-grid { ... }
.product-card { ... }
.tools-grid { ... }
.tools-column { ... }
.tool-item { ... }
.workspace-footer { ... }
.workspace-footer-tools { ... }
.lang-selector { ... }
.hero-image-placeholder { ... }
.ribbon-badge { ... }
```

## Risks / Trade-offs

| Risk | Mitigation |
|---|---|
| CSS 檔案過大 | workspace 樣式集中於單一區段，附註解標示開始/結束 |
| workspace 與 index 共用 Nav 樣式衝突 | workspace 樣式加 `.workspace-` 前綴避免污染 |
| 工具目錄 50+ 項目使 HTML 過長 | 用 JS 陣列動態 render，保持 HTML 乾淨 |
| 首頁 Navbar 改為 genspark 結構後失去原本的 on-page anchor | 保留原本 sections，Nav 只是改顯示文字 |
