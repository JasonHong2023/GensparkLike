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
| 工作空間 | `/workspace/index.html` | 🔄 進行中 | 應用領域頁面切換、3D 知識圖譜 |

---

## 應用領域頁面 / Domain Pages

### 頁面切換機制

左側導航欄點擊應用領域 → 右側主內容區切換顯示對應領域頁面。
點擊「首頁」或「新增」→ 回到工具網格主頁面。

### 領域頁面標籤結構

每個應用領域包含 5 個標籤：

| 標籤 / Tab | 功能 / Function |
|---|---|
| 📌 總覽 | 統計卡片、推薦模板、領域知識 |
| 🔄 工作流 | 該領域的工作流程卡片 |
| ⭐ 技能 | 技能等級和進度卡片 |
| 🧠 知識圖譜 | 3D 互動式知識網絡圖（Three.js） |
| ✏️ 知識圖譜編輯 | 新增和修改知識節點 |

### 3D 知識圖譜設計 / 3D Knowledge Graph Design

使用 **Three.js + WebGL** 建立的 3D 互動式知識圖譜。

**視覺特徵：**

| 元素 / Element | 實現方式 / Implementation |
|---|---|
| 背景 | 深色太空（#050510）+ FogExp2 霧效果 |
| 星空 | 2000 個 PointsMaterial 隨機粒子 |
| 節點 | MeshPhongMaterial 發光球體 + 外層光暈 |
| 標籤 | CanvasTexture 轉 Sprite，懸浮於節點上方 |
| 連線 | LineBasicMaterial 半透明線段 |
| 光源 | AmbientLight + 2 個 PointLight（脈動效果） |

**互動操作：**

| 操作 / Action | 實現方式 / Implementation |
|---|---|
| 拖拉旋轉 | OrbitControls + damping |
| 滾輪縮放 | OrbitControls zoom |
| 點擊節點 | Raycaster 射線偵測 → 彈出詳情模態框 |
| 自動旋轉 | autoRotate（可開關） |
| 節點飄動 | requestAnimationFrame + sin/cos 偏移 |

**節點配色：**

| 層級 / Level | 顏色 / Color | 大小 / Size |
|---|---|---|
| 中心節點 | #3b82f6（藍） | 12 |
| 主要類別 | #60a5fa / #38bdf8 / #818cf8 / #34d399 | 8 |
| 子節點 | #93c5fd / #7dd3fc / #a5b4fc / #6ee7b7 | 5 |
