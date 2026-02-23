# 遊戲研究筆記：類《藥王谷女修修煉手札》開源專案調查

> 調查日期：2026-02-23
> 參考遊戲：[藥王谷女修修煉手札](https://apps.apple.com/tw/app/id6462190343)（HydrozoaWorks Tech Ltd.）

---

## 原版遊戲分析

《藥王谷女修修煉手札》是一款**女性向文字修仙模擬遊戲**，官方稱其為「修仙世界狗血模擬器」。

### 核心機制

| 系統 | 說明 |
|------|------|
| 修煉養成 | 從初入門弟子成長為一代丹修大能 |
| 採藥煉丹 | 收集藥材，配伍遵循中藥禁忌邏輯 |
| 多支線劇情 | 多結局，玩家選擇影響劇情發展 |
| 隨機事件 | 妖獸入侵、秘境開放等突發事件 |
| 門派功法 | 多樣化技能與戰鬥系統（人族八大門派 + 魔族 + 獸族） |
| 戀愛互動 | 與 NPC 結為道侶（女性向重點） |
| 傳承系統 | 角色衰老後可傳承給子嗣 |

---

## GitHub 類似開源專案

### 1. vue-XiuXianGame（最相似、最推薦參考）

- **Repo**: https://github.com/setube/vue-XiuXianGame
- **Stars**: 1.7k+ | **Forks**: 284
- **技術**: Vue.js + Element Plus + Pinia
- **Demo**: https://xiuxian.wenzi.games/
- **授權**: CC BY-NC 4.0（非商業用途可用）

**特色功能：**
- 掛機修煉系統
- 裝備/法寶收集
- 劇情分支與奇遇事件
- 多職業選擇（劍修/符修/丹修）
- 暗黑模式 + H5 自適應
- 離線自動修煉與進度存檔
- 支援 Docker 部署

**適合參考的部分：** 整體架構、修煉系統、事件系統、存檔機制

---

### 2. Cultivation World Simulator（AI 驅動）

- **Repo**: https://github.com/4thfever/cultivation-world-simulator
- **技術**: AI Agent 工作流（LLM 驅動）

**特色功能：**
- 玩家扮演「天道」（上帝視角）
- 每個 NPC 獨立由 LLM 驅動
- 有獨立性格、記憶、人際關係
- 無預設劇本，世界自行演化

**適合參考的部分：** AI 驅動 NPC 的概念、世界觀設計

---

### 3. LifeRestart 人生重開模擬器（事件系統經典）

- **Repo**: https://github.com/VickScarlet/lifeRestart
- **技術**: JavaScript
- **Stars**: 極高（曾經爆紅）

**特色功能：**
- 1500+ 事件池
- 五大屬性系統（智力/體質/家境/快樂/生命）
- 天賦選擇 + 屬性分配
- 文字自動推進人生

**適合參考的部分：** 事件池設計、屬性系統、隨機事件觸發機制

---

### 4. JourneytoImmortalCultivation（AI 即時劇情）

- **Repo**: https://github.com/White-stone36/JourneytoImmortalCultivation
- **技術**: GPT-4 + DALL-E 3

**特色功能：**
- GPT-4 即時生成修仙劇情
- DALL-E 3 根據劇情自動繪製場景
- 每次遊玩都是獨特體驗

**適合參考的部分：** AI 生成劇情的 Prompt 設計

---

### 5. MarkdownGame（文字冒險引擎）

- **Repo**: https://github.com/YicongCao/MarkdownGame
- **技術**: JavaScript

**特色功能：**
- 用 Markdown 編寫遊戲劇本
- 支援劇情分支和變數系統
- 範例劇本：福爾摩斯、哈利波特等

**適合參考的部分：** 劇本引擎的設計思路、分支邏輯

---

## 待討論方向

- [ ] 遊戲風格：純文字模擬 / 視覺小說 / AI 驅動
- [ ] 技術選擇：Vue.js / 純 HTML+JS / 其他框架
- [ ] 主題世界觀：修仙 / 自訂主題
- [ ] 核心玩法優先順序
- [ ] 是否要加入 AI 元素
