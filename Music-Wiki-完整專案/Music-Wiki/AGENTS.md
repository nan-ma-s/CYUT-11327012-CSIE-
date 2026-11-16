# AGENTS.md — Music Wiki 專案開發規範

> AI 助手在新增、修改或整理本專案前，必須先閱讀本文件，並遵守以下規則。

## 1. 專案目的
Music Wiki 是繁體中文音樂知識百科，整理樂理、Keyboard 演奏、音樂製作／混音，以及人聲與現場演唱設備。網站是可長期累積文章的知識庫，不是一次性的展示頁。

## 2. 技術規範
- 使用原生 HTML5、CSS3、Vanilla JavaScript，可直接部署 GitHub Pages。
- 不使用需要伺服器端執行的功能；不引入必須編譯的框架，除非使用者明確要求並更新部署流程。
- 優先使用相對路徑，確保專案部署在 `https://USERNAME.github.io/REPOSITORY/` 時正常。
- 全站使用繁體中文，音樂術語可附英文原文。
- 不得在前端程式碼放入 Token、密碼或私人資料。

## 3. 視覺設計系統
- 風格：Dark music-tech / editorial wiki。
- 背景近黑、深藍灰；卡片使用深色層次；紫色與藍色作為強調色。
- 使用清楚標題階層、充足留白、圓角卡片、細緻邊框。
- CSS 色彩變數集中在 `css/style.css` 的 `:root`：`--bg`、`--surface`、`--surface-2`、`--text`、`--muted`、`--accent`、`--accent-2`、`--border`、`--radius`。
- 動畫克制，尊重 `prefers-reduced-motion`。
- 支援桌面、平板與手機，不可出現水平溢位。

## 4. 網站結構
- `index.html`：首頁、搜尋、分類入口、精選文章。
- `pages/theory.html`：樂理分類。
- `pages/keyboard.html`：Keyboard 分類。
- `pages/production.html`：音樂製作與混音分類。
- `pages/live.html`：人聲與現場分類。
- `articles/<category>/<slug>.html`：單篇文章。
- `css/style.css`：全站共用樣式。
- `js/main.js`：導覽與搜尋互動。
- `assets/images/`：圖片資源。
- `.github/workflows/deploy.yml`：GitHub Pages 自動部署。

每頁沿用共用品牌、導覽列、內容區與頁尾，不得任意另造不一致的版型。

## 5. 文章格式
每篇文章盡可能包含：
1. 清楚的文章標題。
2. 1–2 句摘要。
3. 基本概念。
4. 分段詳細說明。
5. 實際例子（音名、和弦、設定值或操作情境）。
6. 常見錯誤／注意事項。
7. 相關分類或延伸閱讀連結。

內容原則：
- 使用容易理解的繁體中文。
- 參考數值須標示為範例，不可說成唯一標準。
- 不確定的設備規格、軟體版本與介面，不可捏造，應註明需依實際版本確認。
- 不把主觀建議寫成普遍定律，不複製未授權教材或圖片。

## 6. 命名與放置規則
- 檔名使用小寫英文與連字號，例如 `minor-scale.html`。
- 分類頁放 `pages/`；文章放 `articles/<category>/`；樣式放 `css/`；程式放 `js/`。
- 檔名不得有空白、全形符號或 `final2` 等版本尾綴。
- 新增文章後，必須更新對應分類頁的文章卡片；若屬精選內容，也更新首頁索引。

## 7. 導覽與互動
- 導覽標籤固定使用：首頁、樂理、Keyboard、音樂製作、人聲與現場。
- 站內連結使用相對路徑；移動檔案後檢查所有連結。
- 搜尋結果須能開啟正確文章；無結果時顯示友善提示。
- 不使用沒有目的地的 `href="#"` 假按鈕；互動控制必須有實際功能。

## 8. AI 工作流程
1. 先閱讀本文件及相關頁面。
2. 確認任務屬於文章、分類、功能或樣式。
3. 沿用既有 CSS 變數、class 與頁面結構。
4. 只修改完成任務所需檔案，避免無關重構。
5. 新增文章時更新分類頁與需要更新的首頁索引。
6. 檢查相對路徑、圖片 alt、連結與手機版版面。
7. 回報修改檔案、功能及尚未驗證的部分。

## 9. 品質檢查清單
- [ ] HTML 結構完整、標題層級合理。
- [ ] 共用 CSS 與導覽風格一致。
- [ ] 手機與桌面皆可閱讀。
- [ ] 站內連結都指向存在的檔案。
- [ ] 搜尋與按鈕可正常操作。
- [ ] 圖片具有適當 `alt`。
- [ ] 沒有將機密資訊放入前端。
- [ ] GitHub Pages 相對路徑正常。

## 10. 新增文章範本
沿用既有文章頁，保留共用導覽、文章容器與頁尾：

```html
<article class="article-shell">
  <a class="back-link" href="../../pages/theory.html">← 返回樂理</a>
  <header class="article-header">
    <span class="eyebrow">MUSIC THEORY</span>
    <h1>文章標題</h1>
    <p class="article-lead">一至兩句摘要。</p>
  </header>
  <div class="article-content">
    <section><h2>基本概念</h2><p>以繁體中文說明。</p></section>
    <section><h2>實際例子</h2><p>提供例子。</p></section>
    <section><h2>常見錯誤與注意事項</h2><ul><li>注意事項。</li></ul></section>
  </div>
</article>
```

新增後更新分類頁，並確認所有相對路徑正確。
