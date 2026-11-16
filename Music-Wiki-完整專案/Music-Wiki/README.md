# Music Wiki｜音樂知識百科

Music Wiki 是繁體中文音樂知識網站，整理樂理、Keyboard 演奏、音樂製作與混音，以及人聲與現場演唱設備。採用 Dark 音樂科技風格，使用原生 HTML、CSS、JavaScript，可部署至 GitHub Pages。

## 專案特色
- 以 `AGENTS.md` 定義 AI 開發規則，讓新增文章沿用一致架構。
- 四大分類：樂理、Keyboard、音樂製作、人聲與現場。
- 首頁支援關鍵字搜尋與分類篩選。
- 響應式版面，支援桌面、平板與手機。
- 不需建置工具，直接開啟 `index.html` 即可預覽。

## 專案結構
```text
Music-Wiki/
├── AGENTS.md
├── README.md
├── index.html
├── pages/ (theory / keyboard / production / live)
├── articles/ (依分類存放文章)
├── css/style.css
├── js/main.js
├── assets/images/
└── .github/workflows/deploy.yml
```

## 本機預覽
下載或 Clone 專案後，以瀏覽器開啟根目錄 `index.html`。也可使用 VS Code Live Server。

## GitHub 上傳
1. 在 GitHub 建立新的 **Public** Repository，例如 `music-wiki`。
2. 將專案所有檔案上傳到 Repository 根目錄。
3. 確認根目錄有 `index.html`、`AGENTS.md`、`README.md`。
4. 開啟 **Settings → Pages**，將 Source 設為 **GitHub Actions**。
5. 確認 `.github/workflows/deploy.yml` 已上傳。
6. 推送到 `main` 後，Actions 會自動部署；成功後在 Settings → Pages 查看網址。

### Git 指令
```bash
git init
git add .
git commit -m "Initial Music Wiki website"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/music-wiki.git
git push -u origin main
```
將 `YOUR-USERNAME` 換成自己的 GitHub 帳號。

## 網站網址格式
```text
https://YOUR-USERNAME.github.io/music-wiki/
```
這只是格式示例；完成部署後才會真正可瀏覽。

## 如何讓 AI 持續新增內容？
每次提出新需求時，先要求 AI 閱讀根目錄 `AGENTS.md`，例如：

> 請閱讀 AGENTS.md，依照 Music Wiki 規則新增一篇「小調音階」文章，放在 `articles/theory/minor-scale.html`，沿用既有文章版型，並更新 `pages/theory.html` 的文章列表。請檢查所有相對連結。

AGENTS.md 已定義網站定位、視覺風格、資料夾結構、命名規則、文章格式、AI 工作流程與品質檢查，因此 AI 不必每次重新猜測專案規則，就能一致地擴充內容。

## 後續可擴充
- 樂理：五度圈、調號、三和弦、七和弦、和弦進行。
- Keyboard：和弦轉位、左手伴奏、節奏型、移調練習。
- 音樂製作：Compressor、Reverb、Delay、Automation、Fade Out。
- 現場演唱：麥克風種類、增益結構、回授處理、監聽與喇叭。

## 技術備註
本專案為純靜態網站，搜尋在瀏覽器端執行。GitHub Pages 支援靜態 HTML、CSS、JavaScript；本專案不需要後端服務。
