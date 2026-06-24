# 技術棧 / Technology Stack

> 建立 / Created: 2026-06-24
> 版本 / Version: v0.2 — PM Evolutionary Ecosystem
> 狀態 / Status: 鎖定 / Locked

---

## 核心技術棧 / Core Stack

### 前端語言 / Frontend Languages

| 語言 / Language | 版本 / Version | 說明 / Description |
|---|---|---|
| **HTML** | HTML5 | 語意化標籤、meta viewport、preconnect hints |
| **CSS** | CSS3 | Custom Properties、Grid、Flexbox、backdrop-filter、@keyframes |
| **JavaScript** | ECMAScript 2020+ | Vanilla JS，無框架，async/await、Fetch API、localStorage |

### 主要框架 / Main Frameworks

```
無框架依賴 / No Framework
純原生 HTML / CSS / JavaScript
```

**原因 / Reason**:
- 🎯 超輕量級（無 npm 依賴，index.html 自含式）
- 🚀 快速載入（單頁面 <50KB）
- 🔧 易於維護（無編譯步驟，直接編輯即可預覽）
- ♿ 完全無障礙（語意化 HTML）

---

## 核心依賴 / Core Libraries

### 外部 CDN 依賴

| 庫 / Library | 版本 / Version | 用途 / Purpose | 來源 / Source |
|---|---|---|---|
| **marked.js** | ^9.0.0 | Markdown 解析渲染 | jsDelivr CDN |
| **Google Fonts** | latest | 字體堆疊（可選） | fonts.googleapis.com |

### 內部依賴

無。所有邏輯內聯於 HTML 檔案。

---

## 設計系統 / Design System

### CSS 變數鎖定 / CSS Custom Properties

```css
/* 色彩主題 / Color Themes */
--primary:              主色調（預設藍色 #1a56db）
--primary-light:        淺色版本
--primary-dark:         深色版本
--accent:               強調色（天藍 #0ea5e9）
--dark:                 背景深色 (#0f172a)
--bg:                   背景色
--bg-section:           分段背景
--text:                 正文文字
--text-secondary:       次要文字
--border:               邊框顏色

/* 間距與尺寸 / Spacing & Sizing */
--max-w:                容器最大寬度 (1120px)
--radius:               圓角（12px）
--radius-sm:            小圓角（8px）

/* 動畫 / Animation */
--ease:                 cubic-bezier(0.16, 1, 0.3, 1)
```

### 主題系統 / Theme System

支援 **16 色主題**，透過修改 `:root` 變數切換：

1. **企業藍** / Corporate Blue (預設) — #1a56db
2. **翡翠綠** / Emerald Green — #059669
3. **琥珀橙** / Amber Orange — #d97706
4. **玫瑰紅** / Rose Red — #e11d48
5. **夜色紫** / Violet Purple — #7c3aed
6. **海洋青** / Cyan Ocean — #0891b2
7. **石墨黑** / Graphite Black — #1f2937
8. **櫻花粉** / Sakura Pink — #ec4899
9. **極光綠** / Aurora Green — #10b981
10. **冰霜藍** / Frost Blue — #06b6d4
11. **皇室金** / Royal Gold — #f59e0b
12. **熔岩紅** / Lava Red — #dc2626
13. **薄荷綠** / Mint Green — #14b8a6
14. **薰衣草** / Lavender — #a855f7
15. **鋼鐵灰** / Steel Gray — #6b7280
16. **珊瑚粉** / Coral Pink — #f97316

**實現方式 / Implementation**:
- `status/index.html` 主題選擇器
- localStorage 持久化（鍵名：`pmEvoTheme`）
- CSS Custom Properties 動態切換
- 即時預覽，無需重新整理

### 字體堆疊 / Typography Stack

```css
/* UI 正文 */
font-family: system-ui, -apple-system, 'Segoe UI', Roboto, 'Noto Sans TC', sans-serif;

/* 程式碼 / Code */
font-family: 'JetBrains Mono', 'Courier New', monospace;

/* 可選：Google Fonts */
'Inter' (weight: 400, 500, 600, 700)
'Source Serif 4' (weight: 400, 600)
```

---

## 動畫與互動 / Animation & Interaction

### 預設過渡 / Default Transitions

| 效果 / Effect | 時長 / Duration | 緩動 / Easing |
|---|---|---|
| 基礎過渡 / Base transition | 150ms | ease |
| 頁面過渡 / Page transition | 250ms | cubic-bezier(0.16, 1, 0.3, 1) |
| Scroll trigger (fade-up) | 600ms | ease-out |

### 響應式設計 / Responsive Design

| 裝置 / Device | 範圍 / Range | 佈局 / Layout |
|---|---|---|
| 桌機 / Desktop | ≥ 1024px | 多欄網格 |
| 平板 / Tablet | 768-1023px | 2-3 欄 |
| 手機 / Mobile | < 768px | 單欄堆疊 |

---

## 部署與託管 / Deployment & Hosting

### 部署方式 / Deployment Method

```
靜態網頁託管 / Static HTML Hosting
```

### 支援平台 / Supported Platforms

| 平台 / Platform | 狀態 / Status | 配置 / Configuration |
|---|---|---|
| **GitHub Pages** | ✅ 支援 | 自動 (main branch) |
| **Cloudflare Pages** | ✅ 支援 | 自訂部署設定 |
| **任何靜態服務器** | ✅ 支援 | 無需特殊配置 |

### 環境變數 / Environment Variables

無。所有設定透過 HTML 或 localStorage。

---

## 版本管理 / Version Management

### Git 工作流 / Git Workflow

```
main (production)
  ├── backup/v0.1 (上一版本備份)
  └── backup/v0.2 (future...)
```

### Commit 規範 / Commit Convention

```
<type>(<scope>): <description-zh> / <description-en>

Types: feat | fix | refactor | docs | chore
Scopes: homepage | workspace | dashboard | specs | rules
```

範例 / Example:
```
feat(homepage): 新增主題切換器 / Add theme switcher
fix(dashboard): 修正 Markdown 解析錯誤 / Fix Markdown parsing bug
docs(rules): 新增技術棧規範 / Add tech stack specification
```

---

## 相容性 / Compatibility

### 瀏覽器支援 / Browser Support

| 瀏覽器 / Browser | 最低版本 / Min Version | 支援狀態 / Status |
|---|---|---|
| Chrome / Edge | 90+ | ✅ 完全支援 |
| Firefox | 88+ | ✅ 完全支援 |
| Safari | 14+ | ✅ 完全支援 |
| Safari iOS | 14+ | ✅ 完全支援 |

**必要功能 / Required Features**:
- CSS Custom Properties
- CSS Grid & Flexbox
- Fetch API
- localStorage
- ES2020+ (async/await)

### 無障礙 / Accessibility

- 📍 WCAG 2.1 Level AA 目標
- 🎯 語意化 HTML5
- ⌨️ 鍵盤導航
- 🔍 螢幕閱讀器相容

---

## 限制與約束 / Constraints

### 禁止事項 / Prohibited

| 項目 / Item | 原因 / Reason |
|---|---|
| NPM packages | 保持零依賴，減少維護負擔 |
| Framework (React/Vue/etc) | 專案規模不需要，會增加複雜性 |
| Build tools (webpack/vite) | 靜態網頁無需編譯 |
| Backend API | 目前是前端展示，無資料持久化需求 |
| TypeScript | 靜態網頁無需型別檢查 |

### 允許新增 / Allowed Additions

| 項目 / Item | 條件 / Condition |
|---|---|
| 新 CDN 依賴 | 檔案 <50KB，必須有 npm 替代方案 |
| 新 CSS library | 僅限 CSS-only（無 JS），檔案 <30KB |
| 後端 API | 需修改本技術棧文件，經完整討論 |
| Build tool | 需修改本技術棧文件，經完整討論 |

---

## 更新日誌 / Changelog

### v0.2 (2026-06-24) — PM EVO Ecosystem

- ✅ HTML5 / CSS3 / Vanilla JS
- ✅ 16 色主題系統
- ✅ marked.js Markdown 解析
- ✅ localStorage 主題持久化
- ✅ 完全響應式設計
- ✅ 自含式 CSS（無外部樣式表）

### v0.1 (2026-06-20) — GensparkLike Skill Exchange

- 🔄 複製 Genspark.ai 視覺設計
- 🔄 工作空間頁面 (workspace/)
- 🔄 專案狀態 Dashboard (status/)

---

## 規則參考 / Rule Reference

遵守規則 **R9 — 技術棧鎖定**：

> 決定技術棧後，在 specs/stack.md 鎖定版本，
> 未經討論不得引入新的 major dependency。

**本文件鎖定時間 / Lock Date**: 2026-06-24
**鎖定者 / Locked By**: PM EVO Team

---

## 預留欄位 / Reserved

### 未來考量 / Future Considerations

- [ ] PWA 支援（offline mode）
- [ ] Dark mode 自動切換（system preference）
- [ ] Internationalization (i18n)
- [ ] 後端 API 整合（當功能擴展時）
- [ ] 性能監控（Web Vitals）

