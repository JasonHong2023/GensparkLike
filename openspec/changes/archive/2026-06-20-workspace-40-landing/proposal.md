# 工作空間 4.0 登陸頁面 / Workspace 4.0 Landing Page

> 狀態 / Status: Draft
> 建立 / Created: 2026-06-19

---

## 摘要 / Summary

從首頁的「開始探索 / Start Exploring」按鈕點入後，呈現一份與 genspark.ai 版面結構 1:1 相同的「Genspark AI 工作空間 4.0」登陸頁面，包含 Navigation、Hero、定價卡、產品區、工具目錄與 Footer，所有功能先以 placeholder 保留。

---

## 範圍 / Scope

### 包含 / Included

1. `workspace/index.html` — 全新 Genspark AI 工作空間 4.0 完整版面頁面
2. `index.html` 修改 — 「開始探索 / Start Exploring」指向 `workspace/`
3. `index.html` 導航列改為 genspark.ai 結構（首頁 / 技能 / 工作流程 / 雲端硬碟 / 更多）
4. `assets/css/style.css` — 新增 workspace 版面專用樣式（定價卡、產品卡片、工具目錄網格、語言選擇器等）
5. 所有按鈕與連結先放 `#` placeholder，不做功能

### 不包含 / Excluded

1. 任何後端功能（認證、資料庫、API）
2. 實際的 AI 工作空間功能（Skills、Workflows、Drive 等）
3. 點擊技能/工具後的子頁面
4. 語言切換的實際邏輯

---

## 動機 / Motivation

使用者希望 GensparkLike 專案能直接呈現 genspark.ai 的完整首頁視覺效果，作為未來開發的視覺參考與展示用途。保留原本首頁的 Skill Exchange 內容，讓「開始探索」成為通往 Genspark 風格工作空間的入口。

---

## 設計參考 / Design Reference

- https://www.genspark.ai/zh-tw — Genspark AI 工作空間 4.0 繁體中文版
- https://www.genspark.ai/ — 英文版參考
- 配色：黑(#000) / 白(#FFF) / 藍(#0F7FFF)
- 字體：Inter / Source Serif 4 / JetBrains Mono

---

## 成功標準 / Success Criteria

1. `workspace/` 頁面在瀏覽器中呈現與 genspark.ai 一致的版面結構
2. 首頁 Navbar 正確顯示 genspark.ai 風格的導航項目
3. 從首頁點「開始探索」正確導向 `workspace/`
4. 所有按鈕/連結點擊後無動作（`#` placeholder）
5. RWD 響應式版面正確（桌面 / 平板 / 手機）
