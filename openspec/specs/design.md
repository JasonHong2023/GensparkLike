# 設計規格 / Design Specification

> 建立 / Created: 2026-06-19
> 狀態 / Status: 初始版本 / Initial version

---

## 設計系統 / Design System

本專案設計以 Genspark.ai 的視覺語言為基礎，建立技能交換平台的品牌識別。

### 品牌色彩 / Brand Colors

```
Primary:   #000000  (Black)
Primary:   #FFFFFF  (White)
Accent:    #0F7FFF  (Blue)

Neutral:   Gray-50 到 Gray-900
```

### 字體系統 / Typography

- **Inter** — UI 文字（導航、按鈕、卡片標題）
- **Source Serif 4** — 內文（部落格、說明文字）
- **JetBrains Mono** — 程式碼/技術內容

### 設計原則 / Design Principles

1. 簡潔、現代、futuristic 深色主題
2. 毛玻璃效果導航（backdrop-filter blur）
3. 漸層背景與微光暈裝飾
4. 流暢的過渡動畫與 hover 效果
5. 全響應式（桌機/平板/手機）

---

## 頁面清單 / Page Inventory

| 頁面 | 路徑 | 狀態 |
|---|---|---|
| 首頁 Landing Page | `/index.html` | ✅ 完成 |
| 專案狀態 Dashboard | `/status/index.html` | 🔄 進行中 |
