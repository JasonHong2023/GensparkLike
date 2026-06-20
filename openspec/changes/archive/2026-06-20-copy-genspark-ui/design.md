# 設計規格 / Design Specification

> 建立 / Created: 2026-06-19

---

## 1. 品牌系統 / Brand System

### 1.1 色彩 / Colors

```
Primary Black   #000000  — 主色（深色背景）
Primary White   #FFFFFF  — 主色（淺色背景/文字）
Accent Blue     #0F7FFF  — 強調色（CTA、連結、焦點元素）

Neutral Gray-50  #F8F9FA  — 極淺灰（卡片背景）
Neutral Gray-100 #F0F1F3  — 淺灰（分隔線）
Neutral Gray-200 #E2E4E8  — 邊框
Neutral Gray-500 #8B8FA3  — 次要文字
Neutral Gray-700 #4A4D59  — 主要文字（淺色主題）
Neutral Gray-900 #1A1B1E  — 深色主題背景層
```

### 1.2 字體 / Typography

```
Font Stacks:
  --font-sans:    'Inter', system-ui, -apple-system, sans-serif
  --font-serif:   'Source Serif 4', Georgia, serif
  --font-mono:    'JetBrains Mono', 'Fira Code', monospace

Size Scale:
  --text-xs:    0.75rem  (12px)
  --text-sm:    0.875rem (14px)
  --text-base:  1rem     (16px)
  --text-lg:    1.125rem (18px)
  --text-xl:    1.25rem  (20px)
  --text-2xl:   1.5rem   (24px)
  --text-3xl:   2rem     (32px)
  --text-4xl:   2.5rem   (40px)
  --text-5xl:   3.5rem   (56px)
  --text-6xl:   4.5rem   (72px)
```

### 1.3 Logo

GensparkLike 使用文字 Logo `GensparkLike` 搭配星形圖示，
與 Genspark 的 star motif 呼應但風格微調。

---

## 2. 頁面佈局 / Page Layout

```
┌──────────────────────────────────────────────────────────┐
│  ■ 導航列 Navbar (fixed top, 透明→滾動後毛玻璃)           │
│  ┌──────┐  ┌──┐ ┌──┐ ┌──┐ ┌──┐ ┌──┐ ┌─────────────┐   │
│  │ Logo │  │Home│Skills││Exch.││...││ Get Started │   │
│  └──────┘  └──┘ └──┘ └──┘ └──┘ └──┘ └─────────────┘   │
├──────────────────────────────────────────────────────────┤
│                                                           │
│  ■ Hero 區 (全螢幕，深色背景，動態效果)                    │
│    ┌──────────────────────────────────────┐               │
│    │ 大標題：Skill Exchange Platform      │               │
│    │ 副標：Connect. Learn. Grow.          │               │
│    │ [CTA: Start Exploring] [Learn More]  │               │
│    │ 背景：gradient + 網格/星形裝飾       │               │
│    └──────────────────────────────────────┘               │
│                                                           │
│  ■ Feature 區 (多欄卡片網格)                              │
│    ┌──────┐ ┌──────┐ ┌──────┐                            │
│    │Card 1│ │Card 2│ │Card 3│                            │
│    └──────┘ └──────┘ └──────┘                            │
│                                                           │
│  ■ Category 區 (技能分類 badges)                          │
│    ┌──┐ ┌──┐ ┌──┐ ┌──┐ ┌──┐ ┌──┐                       │
│    │程式│ │設計│ │語言│ │音樂│ │運動│ │料理│               │
│    └──┘ └──┘ └──┘ └──┘ └──┘ └──┘                       │
│                                                           │
│  ■ How It Works 區 (步驟流程)                             │
│                                                           │
│  ■ CTA 區 (倒數第二個行動呼籲)                            │
│                                                           │
│  ■ Footer (四欄)                                          │
│    Products | Categories | Company | Social               │
│                                                           │
└──────────────────────────────────────────────────────────┘
```

---

## 3. 視覺風格 / Visual Style

### 3.1 導航列 / Navbar

- Fixed top, 初始透明，scroll > 80px 後 backdrop-blur 毛玻璃
- Logo 左側，導航連結居中，CTA 按鈕右側
- 使用 Inter Medium, 14px

### 3.2 Hero 區域

- 全螢幕高度 (`100vh`)，深色背景
- 背景：`#000 => #0a0a0f` 漸層 + 微網格 overlay
- 大標題：白色，Inter Bold，~72px
- 副標：灰色，Inter Regular，~20px
- CTA 按鈕：藍色 `#0F7FFF`，hover 微亮
- 可選動畫：出現時的 fade-in-up 動畫

### 3.3 Feature 卡片

- 圓角 `border-radius: 12px`
- 淺色背景 (white or gray-50)，深色文字
- 圖示 + 標題 + 簡短描述
- 3 欄網格 (2xl: 3 col, lg: 2 col, mobile: 1 col)
- Hover 時微上移 + shadow 加深

### 3.4 Footer

- 深色背景 (`#111`)
- 四欄 + 版權聲明
- 字體 14px，灰色文字

---

## 4. 響應式 / Responsive Breakpoints

```
Desktop (>1024px):    完整 3-4 欄網格
Tablet (768-1024px):  2 欄網格，縮小字體
Mobile (<768px):      單欄堆疊，漢堡選單
```

---

## 5. 目錄結構 / File Structure

```
GensparkLike/
├── index.html               ← 首頁（最終版本）
├── status/
│   └── index.html           ← 專案狀態 dashboard
├── assets/
│   ├── css/
│   │   └── style.css        ← 主樣式表
│   ├── js/
│   │   └── main.js          ← 互動 JS
│   └── images/
│       ├── logo.svg
│       ├── hero-bg.svg
│       └── ...
├── openspec/
│   ├── specs/
│   │   └── rules.md
│   └── changes/
│       └── copy-genspark-ui/
│           ├── proposal.md
│           ├── design.md
│           └── tasks.md
```
