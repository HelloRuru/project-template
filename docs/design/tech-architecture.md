# 技術架構設計

> 最後更新：2026-02-23

---

## 技術選擇

| 層級 | 技術 | 原因 |
|------|------|------|
| 前端框架 | Next.js (App Router) | SSR/SSG 支援，適合文字遊戲，SGE 友善 |
| 樣式 | Tailwind CSS | 快速開發，響應式設計容易 |
| 驗證 | Supabase Auth | 內建 Email/密碼，免費額度高 |
| 資料庫 | Supabase PostgreSQL | 關聯式資料庫，適合遊戲存檔 |
| 即時同步 | Supabase Realtime | 內建 WebSocket |
| 部署 | Cloudflare Pages | 符合現有工作流 |
| 狀態管理 | Zustand | 輕量，適合遊戲狀態 |

---

## 資料庫結構（初步規劃）

```
核心表格：
├── users              帳號資訊
├── characters         角色資料（位份、屬性、世代）
├── inventory          道具背包
├── relationships      NPC 好感度與關係
├── family_tree        家族譜系（世代傳承核心）
├── events_log         事件紀錄
├── story_progress     劇情進度
└── save_states        存檔快照
```

---

## 存檔機制

### 自動存檔觸發點

| 時機 | 說明 |
|------|------|
| 進入新關卡 / 章節前 | 防止進度丟失 |
| 做出重大決定前 | 結盟、背叛、下毒等 |
| 懷孕 / 生產事件 | 重要里程碑 |
| 位份變動 | 晉升或降位 |
| 世代傳承切換前 | 最關鍵的存檔點 |
| 每日自動存檔 | 防當機、網頁跳掉 |

### 存檔策略

```
1. 即時存檔：每次重要操作後寫入 Supabase
2. 防抖存檔：debounce 2-3 秒，避免頻繁寫入
3. 離線快取：localStorage 暫存，恢復網路後同步
4. 衝突處理：以伺服器端時間戳為準
5. 多存檔位：5 個手動存檔 + 1 個自動存檔
6. 關鍵存檔：進關卡、做重大決定前強制存檔
```

### 跨裝置同步

- 登入後自動載入雲端最新存檔
- 偵測到本地存檔較新時，提示玩家選擇
- 登出時自動上傳當前進度

---

## 響應式設計（Mobile-first）

### 斷點

- Mobile：< 768px（最重要）
- Tablet：768-1023px
- Desktop：>= 1024px

### 手機體驗重點

- 單手操作友善
- 文字大小適中（最小 16px）
- 按鈕觸控區域 >= 44px
- 底部固定操作列
- 滑動切換場景
- 避免需要精確點擊的 UI

---

## 開源引擎參考

| 引擎 | 語言 | 特色 | 網頁支援 |
|------|------|------|---------|
| Ren'Py | Python | 最成熟視覺小說引擎 | 可匯出 Web |
| Ink (Inkle) | C# | 強大分支敘事語言 | 有 JS 版 inkjs |
| Twine | JavaScript | 開源互動小說工具 | 原生 Web |
| monogatari | JavaScript | 視覺小說網頁引擎 | 原生 Web |

### 之前研究的開源專案

| 專案 | 技術 | 可參考部分 |
|------|------|-----------|
| vue-XiuXianGame | Vue.js + Pinia | 整體架構、事件系統、存檔機制 |
| LifeRestart | JavaScript | 事件池設計、屬性系統 |
| MarkdownGame | JavaScript | 劇本引擎、分支邏輯 |
