# HelloRuru 新專案模板

@AGENTS.md

## 啟動流程（進入此 repo 時自動執行）

當你開啟這個 repo 的 session 時，請立刻執行以下流程：

1. **向嚕寶打招呼**，告知這是專案模板
2. **詢問嚕寶**：
   - 「要用這個模板建立新的 repo 嗎？」
   - 如果要 → 詢問新 repo 名稱（例如 `my-new-project`）
   - 確認後執行：
     ```
     gh repo create HelloRuru/{名稱} --template HelloRuru/project-template --public --clone
     ```
3. **建立後**：
   - 進入新 repo 目錄
   - 請嚕寶描述專案用途
   - 根據描述更新 CLAUDE.md 的專案資訊和規則
   - commit + push 到 main

## 模板內容

這個 repo 是 HelloRuru 所有新專案的起點，包含：

- `AGENTS.md` — 小八人設 + DS v1.9 + Git 規則（網頁版 Claude 會自動讀取）
- `CLAUDE.md` — 本檔案（建立新 repo 後會被改寫為專案專屬規則）
- `.gitignore` — 基本忽略清單

## 專案骨架（新 repo 建立後請改寫以下內容）

### 專案資訊

- 網址：（填入）
- Repo：HelloRuru/（填入）
- 部署：（Cloudflare Pages / GitHub Pages / 其他）

### 專案規則

（在這裡寫這個專案專屬的規則）
