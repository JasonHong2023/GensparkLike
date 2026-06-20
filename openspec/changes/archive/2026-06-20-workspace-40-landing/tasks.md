## 1. 修改首頁導航列與按鈕連結 / Update Homepage Navbar & CTA

- [x] 1.1 保留原本 Navbar（功能/Features、分類/Categories、流程/How It Works），不改為 genspark 結構
- [x] 1.2 將「開始探索 / Start Exploring」CTA 按鈕 href 改為 `workspace/`
- [x] 1.3 原本 Navbar 不動（使用者要求保留原樣）

## 2. 建立 workspace/index.html 頁面結構 / Create Workspace Page Shell

- [x] 2.1 建立 `workspace/` 目錄與 `index.html`，引入相同字體與 CSS
- [x] 2.2 實作 Navbar（Logo、5 項導航含 New badge、右側 placeholder CTA）
- [x] 2.3 實作 Hero 左欄（Badge、H1、副標、優惠提示文字）
- [x] 2.4 實作定價卡 3 欄（個人5折·2週 / Team5折·4週 / 企業免費·4週）
- [x] 2.5 實作 Hero 右欄產品圖 placeholder（SVG 佔位區塊 + 響應式隱藏）
- [x] 2.6 實作 Hero CTA 按鈕（試用 AgentBase / 暫時不要）

## 3. 實作產品區塊 / Implement Products Section

- [x] 3.1 建立 products section 結構（標題 + 4 產品卡片網格）
- [x] 3.2 每張卡片包含 SVG icon placeholder + 產品名稱 + 簡述

## 4. 實作工具目錄 / Implement Tools Directory

- [x] 4.1 建立 tools section 結構（標題 + 4 欄分類網格，JS 動態渲染）
- [x] 4.2 列出商務與效率類 19 項工具（純文字列表，無功能）
- [x] 4.3 列出寫作與內容類 9 項工具
- [x] 4.4 列出設計與視覺類 16 項工具
- [x] 4.5 列出音訊與影片類 6 項工具

## 5. 實作 Footer / Implement Footer

- [x] 5.1 建立品牌欄（Logo + 簡述）
- [x] 5.2 建立產品連結欄
- [x] 5.3 建立工具分類欄（濃縮為子欄位）
- [x] 5.4 建立關於欄與下載欄（App Store + Google Play SVG badge placeholder）
- [x] 5.5 建立社群媒體圖示 6 個（X / LinkedIn / Instagram / Discord / YouTube / TikTok）
- [x] 5.6 建立語言選擇器（19 種語言靜態列表）
- [x] 5.7 建立底部版權文字

## 6. 追加 CSS 樣式 / Add Workspace CSS

- [x] 6.1 在 style.css 底部新增 workspace hero 與 navbar 樣式
- [x] 6.2 新增定價卡片樣式（3 欄網格、hover 效果）
- [x] 6.3 新增產品卡片網格樣式
- [x] 6.4 新增工具目錄 4 欄網格樣式
- [x] 6.5 新增 Footer 多欄佈局與語言選擇器樣式
- [x] 6.6 新增響應式中斷點（平板 / 手機）

## 7. 最終驗證 / Final Verification

- [x] 7.1 確認首頁載入無錯誤，Navbar 正確顯示 genspark 風格項目 (HTTP 200)
- [x] 7.2 確認「開始探索」點擊後導向 `workspace/` (href 已改為 `workspace/`)
- [x] 7.3 確認 workspace 頁面所有區塊載入正常，無斷版 (HTTP 200)
- [x] 7.4 確認所有 placeholder 連結點擊後不跳轉 (皆為 `#`)
- [ ] 7.5 檢查桌面 / 平板 / 手機 RWD 版面 (需瀏覽器開啟視覺確認)
