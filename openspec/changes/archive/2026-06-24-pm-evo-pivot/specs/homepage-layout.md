# 規格：首頁版面 / Spec: Homepage Layout

## 規格說明 / Description

PM Evolutionary Ecosystem 首頁，包含 Header、Hero、About、Pain Points、Features、How It Works、CTA、Footer 八個區塊，支援 16 色主題切換與滾動動畫。

## 驗證方式 / Verification

| 項目 / Item | 驗證方式 / Verification | 完成條件 / Completion Criteria |
|---|---|---|
| Header | 瀏覽器開啟，滾動頁面 | fixed top，滾動後毛玻璃效果，Nav 連結正確 |
| Hero | 檢視首屏內容 | 大標題含 gradient highlight、副標、兩個 CTA、統計數字、背景裝飾 |
| About | 檢視 About 區塊 | 左文右 4 卡片網格，數字正確顯示 |
| Pain Points | 檢視痛點區塊 | 4 張卡片，每張含痛點描述 + 解決方案 badge |
| Features | 檢視功能區塊 | 4 張特徵卡片，含 SVG 圖示 + 標題 + 說明 |
| How It Works | 檢視流程區塊 | 3 步驟（選模板→填資訊→交付），含連接線 |
| CTA | 檢視 CTA 區塊 | gradient 背景藍色區塊，含按鈕指向 workspace/ |
| Footer | 檢視 Footer | 4 欄（產品/資源/聯絡/品牌），版權宣告 |
| 主題切換器 | 點擊左側 🎨 按鈕 | 面板展開，選擇任一主題後頁面配色即時切換 |
| 主題持久化 | 選主題後重新整理頁面 | 主題保持不變 |
| 滾動動畫 | 滾動頁面 | fade-up 元素進入視口時顯示動畫 |
| RWD 桌機 | viewport ≥1024px | 多欄佈局正常，無斷版 |
| RWD 平板 | viewport 768-1023px | 欄位自動重排 |
| RWD 手機 | viewport <768px | 單欄佈局，Nav 隱藏 |
