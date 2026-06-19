# 開發進度記錄

## 2026-06-17（初始建立）

### 完成事項

1. **主題確認與教材蒐集**
   - 搜尋「新手如何學習 AI Agent」相關教材
   - 選定主要來源：LearnAgent.org、Datawhale Agent-Learning-Hub、多篇 2026 入門指南

2. **大綱設計（outline.md）**
   - 10 頁簡報大綱，從「什麼是 Agent」到「行動清單」
   - 經使用者確認後定案

3. **HTML 簡報生成（index.html）**
   - 使用 html-slide-builder skill 生成 Reveal.js 5.1 簡報
   - 採用深色主題 + 手繪技術風視覺風格
   - 使用 CSS 元件：title-slide、adv-grid、stat-row、timeline、vs-grid、conclusion-grid、project-card

4. **背景底圖生成**
   - 使用 Pollinations.ai（免費 API）生成封面與封底背景
   - 腳本：`html-slide-builder/scripts/draw.py`

5. **圖標系統**
   - 生成 icon_sheet（Observe / Think / Act 三合一）
   - 使用 Pillow 裁切與縮放為獨立 256x256 PNG
   - 去背保留透明背景

6. **VIZ 滑桿互動**
   - 第 4 頁：學習路線滑桿對比（基礎 vs 進階）
   - 修正：左右圖層使用雙向 clip-path 避免文字重疊

7. **GitHub Pages 部署**
   - Repo：kunlongkuo/ai-agent-learning
   - URL：https://kunlongkuo.github.io/ai-agent-learning/

### 修改的重要檔案

| 檔案 | 說明 |
|------|------|
| `index.html` | 主簡報（395 行，10 頁 + CSS + JS） |
| `images/cover.png` | 封面背景底圖，91866 bytes |
| `images/ending.png` | 封底背景底圖，34471 bytes |
| `images/icon_observe.png` | 觀察圖標，1314 bytes |
| `images/icon_think.png` | 思考圖標，1250 bytes |
| `images/icon_act.png` | 行動圖標，6326 bytes |

### 做出的關鍵決策

1. **選擇 html-slide-builder 而非 codex-ppt** — 因 OpenAI API 達到用量上限，無法使用 gpt-image-2 生圖，轉用 Pollinations.ai（免費）生成背景底圖，並產出 HTML 簡報
2. **不使用 Firebase 互動元件** — 為保持專案零相依性，跳過文字雲/投票元件
3. **深色主題 + 手繪風格** — 經使用者確認選擇手繪技術解釋風

### 目前卡住的問題

無。簡報已可正常播放與部署。

### 下次接手先看

1. `AGENTS.md` — 給 AI 的交接文件
2. `README.md` — 專案總覽與啟動方式
3. `index.html` — 主要修改檔案，CSS 元件集中在 `<style>` 區塊
4. 若想新增互動功能，先讀 `html-slide-builder/references/firebase-config.md`
