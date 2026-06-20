# GensparkLike 專案規則 / Project Rules

> 生效日期 / Effective Date: 2026-06-19
> 所有規則在經過討論修改前永久有效 / All rules remain in effect until modified through discussion.

---

## R1 — 雙語註解 / Bilingual Comments

```
所有註解內容都要用繁體中文 + 英文並列書寫
All comments must be written in Traditional Chinese and English
```

```typescript
// 初始化搜尋引擎 / Initialize search engine
function initSearch() { ... }

// 計算 token 數量 / Calculate token count
const count = tokens.length;

/**
 * 根據 query 產生 Sparkpage / Generate Sparkpage from query
 * @param query - 使用者輸入的搜尋字串 / User's search string
 */
```

🚫 禁止：只有單語註解（僅中文或僅英文）

---

## R2 — 重大變更前 GitHub 備份 / GitHub Backup Before Major Changes

```
當前後版本的程式計畫更動相差大於 25%
（以 feature/task 數量衡量），
必須先開一個新的 branch 保存上一版，再繼續進行。
```

**衡量方式 / Measure**: feature/task 數量對比
**備份方式 / Backup method**: 開新 branch（`git checkout -b backup/v<version>`）

```
當前版本 v0.2 計畫新增 8 個 task
對比上一版 v0.1 只有 6 個 task
變動量 = (8-6)/6 ≈ 33% → 大於 25%

    ┌──────────────────────────┐
    │  先開 branch 備份 v0.1   │
    │  git checkout -b backup/v0.1
    │  git push origin backup/v0.1
    └──────────────────────────┘
                    │
                    ▼
    ┌──────────────────────────┐
    │  回 main 繼續開發 v0.2   │
    └──────────────────────────┘
```

---

## R3 — 文件同步紀律 / Documentation Sync Discipline

```
每次對以下檔案有更動時，必須仔細記錄並同步更新：
```

| 文件 / Document | 說明 / Description |
|---|---|
| `proposal.md` | 變更提案 / Change proposal |
| `tasks.md` | 任務清單 / Task list |
| `specs/` | 規格定義 / Specifications |
| `design.md` | 設計文件 / Design document |

**原則 / Principle**：不允許「程式碼先寫，文件之後再補」。每一次 commit 或 change 完成前，先確認四者一致。

---

## R4 — 討論優先於實作 / Discussion Before Implementation

```
任何更動都必須先討論，討論完畢並詢問確認後，才進行實作。
```

**流程 / Workflow**:

```
討論 / Explore (/opsx-explore)
  │
  ▼
確認方向 / Confirm direction
  │
  ▼
建立變更 / Propose change (/opsx-propose)
  │
  ▼
審閱提案（proposal.md / design.md / tasks.md）
Review proposal
  │
  ▼
明確回覆「可以實作」
User confirms "ready to implement"
  │
  ▼
開始實作 / Start implementation (/opsx-apply)
```

🚫 禁止行為 / Prohibited:
- 聊到一半直接開寫 / Coding during discussion
- 沒有明確確認就實作 / Implementing without explicit confirmation
- 邊討論邊修改程式碼 / Modifying code while discussing

---

## R5 — Commit 紀律 / Commit Discipline

```
每個 task 完成後就做一次 commit。
禁止一個 commit 包含多個不相關的 task。
```

**Commit message 格式 / Format**:

```
<type>(<scope>): <簡短描述>
<type>(<scope>): <brief description>
```

**Types**: `feat` | `fix` | `refactor` | `docs` | `chore`

**範例 / Example**:
```
feat(search): 新增多 agent 平行搜尋 / Add multi-agent parallel search
fix(sparkpage): 修正來源渲染錯誤 / Fix source rendering error
docs(rules): 新增 commit 紀律規則 / Add commit discipline rule
```

---

## R6 — 不做的清單 / Anti-Patterns (禁止清單)

```
以下行為列入禁止清單，如發現應立即停止並討論替代方案：
```

| # | 禁止行為 / Prohibited Behavior | 原因 / Reason |
|---|---|---|
| 6.1 | 使用 `any` / `@ts-ignore` / `@ts-expect-error` 繞過型別檢查 | 型別安全崩壞 |
| 6.2 | 空 catch block `catch(e) {}` | 忽略錯誤 = 未爆彈 |
| 6.3 | 直接修改 `node_modules` 或 vendor 目錄 | 變更不可追溯 |
| 6.4 | 在沒有先讀取檔案的狀況下編輯（AI agent 適用） | 憑空猜測造成破壞 |
| 6.5 | 硬編碼敏感資訊（API key、secret 等） | 資安風險 |
| 6.6 | 刪除 failing test 來讓 build 通過 | 欺騙驗證 |

---

## R7 — 每條 Spec 都要有驗證標準 / Every Spec Must Have Verification Criteria

```
每個 spec 必須明確定義「怎麼知道做完了」：
```

**模板 / Template**:

| 欄位 / Field | 內容 / Content |
|---|---|
| 規格說明 / Description | 什麼功能 / What feature |
| 驗證方式 / Verification | 怎麼測、怎麼看 / How to test or observe |
| 完成條件 / Completion Criteria | 具體 observable 的結果 / Specific observable result |

**範例 / Example**:

| 項目 / Item | 內容 / Content |
|---|---|
| 規格 / Spec | 搜尋結果顯示來源 |
| 驗證方式 / Verification | 輸入 query，檢查是否有來源連結 |
| 完成條件 / Completion | 每條結果都附有可點擊的來源 URL |

---

## R8 — Task 粒度假設 / Task Granularity Default

```
除非特別說明，預設每個 task 的實作範圍：
```

| 維度 / Dimension | 限制 / Limit |
|---|---|
| 檔案數 / Files | 1-3 個 |
| 行數 / Lines | ≤ 250 行純邏輯（不含註解、空行） |
| 時間 / Time | 單一 session 可完成 |

超過上述範圍 → 需拆分 task。

---

## R9 — 技術棧鎖定 / Tech Stack Lock

```
決定技術棧後，在 specs/stack.md 鎖定版本，
未經討論不得引入新的 major dependency。
```

**鎖定項目 / Locked items**:
- 語言版本 / Language version
- 主要框架 / Main framework
- 核心 library / Core libraries
- LLM provider / API

---

## R10 — Session 結束前更新記錄 / End-of-Session Update

```
每個開發 session 結束前：
```

1. 確認所有 opened tasks 狀態正確（done / pending）
2. 確保 proposal.md 與實際進度一致
3. 如果還有 pending tasks，寫一段簡短摘要給下次繼續

---

## R11 — 開發伺服器使用非標準 PORT / Development Server Uncommon Port

```
任何專案的開發伺服器（dev server），
禁止使用常見的預設 PORT（80, 443, 3000, 5173, 8080, 8000, 5000, 9000 等），
必須使用最不常用的 PORT 號碼以避免衝突。
```

**慣例 / Convention**: 使用 PORT **21473** 或 **9432** 或其他非常用 PORT。

**範例 / Example**:
```bash
# ✅ 正確：使用不常用 PORT
python3 -m http.server 21473

# ❌ 錯誤：使用常見 PORT
python3 -m http.server 8080     # 禁止
python3 -m http.server 3000     # 禁止
npx vite                        # 預設 5173，禁止
```

---

## R12 — 文件視覺呈現：網站地圖或流程圖 / Visual Documentation: Site Map or Flow Chart

```
專案的開發文件與狀態呈現，依照專案類型選擇視覺輔助圖：

  網頁呈現（Web / Frontend / UI） → 網站地圖（樹狀結構）
  程式碼呈現（API / Library / CLI） → 流程圖
```

**網站地圖 / Site Map** — 以樹狀結構顯示專案目錄與頁面關係：

```
GensparkLike/
├── index.html                 ← 首頁 Landing Page
├── assets/
│   ├── css/style.css
│   └── js/main.js
├── status/
│   └── index.html             ← 專案 Dashboard
└── openspec/
    ├── specs/                 ← 規格文件
    └── changes/               ← 變更記錄
```

**流程圖 / Flow Chart** — 以流程圖顯示程式邏輯或架構（API 路由、資料流、狀態機等）

---

## R13 — 六項文件同步自動更新 / Six-Item Auto-Sync Dashboard

```
專案狀態 Dashboard 必須涵蓋以下六個項目，
每個項目的內容在檔案更動時自動更新（網頁質感不應妥協）：
```

| # | 項目 / Item | 說明 / Description |
|---|---|---|
| 1 | `proposal.md` | 變更提案 / Change proposal |
| 2 | `tasks.md` | 任務清單 / Task list |
| 3 | `specs/` | 規格定義 / Specifications |
| 4 | `design.md` | 設計文件 / Design document |
| 5 | 專案規則 / Rules | 已建立的專案規則集 |
| 6 | 網站地圖 / Site Map | 以樹狀結構呈現專案目錄（網頁專案） |
|   | 流程圖 / Flow Chart | 流程圖呈現（程式碼專案） |
