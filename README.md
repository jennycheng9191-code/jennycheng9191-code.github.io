# jennycheng9191-code.github.io

所有自建網站的入口主頁。網址就是 GitHub Pages 的根目錄：

**https://jennycheng9191-code.github.io/**

這個 repo 名稱和 GitHub 帳號同名，所以它佔的是網域根目錄；其他 repo 的網站照舊在 `/repo名/` 底下，網址完全不受影響。

## 怎麼新增一個站

編輯 `sites.json`，在對應 group 的 `items` 加一筆，然後 push。約一分鐘後主頁就會出現。

```json
{
  "name": "中文站名",
  "repo": "repo 名",
  "url": "https://jennycheng9191-code.github.io/repo名/",
  "desc": "一句用途說明",
  "scope": "涵蓋範圍",
  "freq": "更新頻率",
  "gated": true,
  "accent": "#3C8EA0",
  "repoUrl": "https://github.com/jennycheng9191-code/repo名"
}
```

- `gated: true` 會顯示「🔒 需要密碼」標記。**密碼本身不寫在這裡**，前端密碼閘的驗證碼就在網頁檔案裡，把密碼印在公開頁面上等於整套白做。
- `isRepo: true` 用在沒有公開網頁的 private repo（如 bond-yields），卡片上的字會變成「看 GitHub repo」。
- `accent` 是卡片左側色條，沿用總經站的配色（`#D85A30` 通膨橙／`#185FA5` 勞動藍／`#3C8EA0` 金融青／`#7A8B2F` 財政綠／`#534AB7` 信心紫／`#D9A441` 黃）。
- 記得順手改 `updated` 日期。

## 技術

純靜態 HTML，沒有建置步驟、沒有相依套件、沒有排程。Pages 直接服務 main 分支根目錄。配色沿用 `us-macro-guide` 的深色系（`#0E1116`）。

本機預覽：

```bash
cd "C:\Users\Jenny Cheng\Projects\jennycheng9191-code.github.io"
python -m http.server 4318
```

然後開 http://127.0.0.1:4318/ （直接雙擊 `index.html` 不行，瀏覽器會擋 `sites.json` 的讀取）。
