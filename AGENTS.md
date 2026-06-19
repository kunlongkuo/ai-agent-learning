# AGENTS.md — AI 交接文件

## 專案概述

Reveal.js 互動簡報，主題「新手如何學習 AI Agent」，10 頁。

## 重要檔案

| 檔案 | 說明 |
|------|------|
| `index.html` | **唯一需修改的檔案**。所有 CSS（含元件樣式）、HTML 結構、JS 邏輯都在這裡 |
| `images/*.png` | 靜態資源，被 index.html 引用。重新生成時注意路徑 |
| `docs/PROGRESS.md` | 開發歷程記錄，接手前先看 |

## 修改規則

1. **只改 `index.html`** — 圖片不需修改，除非要更換背景風格
2. **CSS 元件庫**在 `<style>` 區塊（第 14-92 行），Components：title-slide、stat-row、adv-grid、vs-grid、timeline、conclusion-grid、project-card
3. **每頁內容**在 `<div class="slides">` 內的 `<section>`，共 10 頁
4. **VIZ 滑桿邏輯**在最後的 `<script>` 中，修改需同時更新 CSS clip-path

## 常用操作

- 新增一頁：複製一個 `<section>` 區塊，選用元件 class
- 更換背景圖：修改 `data-background-image` 屬性，透明度用 `data-background-opacity`
- 調整 fragment 動畫：在元素上加 `class="fragment"`
- 修改滑桿對比內容：更新 `.viz-before` 和 `.viz-after` 內部的 HTML

## 部署方式

```bash
git add .
git commit -m "feat: 簡短說明改動"
git push
```

GitHub Pages 自動更新（約 1-3 分鐘生效）。

## 已對齊的 AI Skills

- `codex-ppt` — 最初規劃大綱用
- `html-slide-builder` — 生成 HTML 與 deploy 流程
- `draw` — 生圖（未成功，改用 Pollinations）
