# 設計規格 / Design Specification

> 建立 / Created: 2026-06-19
> 最後更新 / Last Updated: 2026-06-24
> 狀態 / Status: v0.2 — PM EVO Ecosystem

---

## 品牌定位 / Brand Position

PM Evolutionary Ecosystem — 為產品經理打造的 AI 工作平台。
核心訴求：告別從零開始的文件地獄。

## 設計系統 / Design System

### 品牌色彩 / Brand Colors (Default: Corporate Blue)

```
Primary:       #3b82f6  (Blue)
Primary Light: #60a5fa
Primary Dark:  #1e40af
Accent:        #38bdf8  (Sky)
Background:    #0f172a  (Dark)
Bg Section:    #1a2332
Text:          #f1f5f9
Text Muted:    #94a3b8
```

主題系統：支援 16 色主題（企業藍 / 翡翠綠 / 琥珀橙 / 玫瑰紅 / 夜色紫 / 海洋青 / 石墨黑 / 櫻花粉 / 極光綠 / 冰霜藍 / 皇室金 / 熔岩紅 / 薄荷綠 / 薰衣草 / 鋼鐵灰 / 珊瑚粉），透過 CSS custom properties 切換。

### 字體系統 / Typography

- **系統字體堆疊**: `system-ui, -apple-system, 'Segoe UI', Roboto, 'Noto Sans TC', sans-serif`
- 標題: 極粗 (800) + tight letter-spacing
- 內文: 18px base, line-height 1.7-1.9

### 設計原則 / Design Principles

1. 深色主題優先（dark-first），淺色備用
2. 毛玻璃導航（backdrop-filter blur）
3. 網格背景裝飾（微線條 + 點陣紋理）
4. fade-up 滾動觸發動畫
5. 全響應式（桌機 1024+ / 平板 768-1023 / 手機 <768）
6. CSS 自含式（所有樣式內聯於 index.html，無外部依賴）

### 頁面清單 / Page Inventory

| 頁面 / Page | 路徑 / Path | 狀態 / Status | 驗證方式 / Verification |
|---|---|---|---|
| 首頁 Landing Page | `/index.html` | ✅ 完成 | 瀏覽器開啟，8 區塊正常顯示 |
| 專案 Dashboard | `/status/index.html` | 🔄 進行中 | 六項文件同步自動載入 |
| 工作空間 | `/workspace/index.html` | 🟡 待改造 | 標題更新為 PM EVO，版面待全面改造 |
