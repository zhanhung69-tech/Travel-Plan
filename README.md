# 旅遊規劃系統

這是一個可直接用瀏覽器開啟的旅遊規劃工具，支援目的地資料、行程靈感、逐日行程、航班住宿、票券、預算試算、共同記帳、行李清單、照片紀錄、PDF/CSV/ICS/JSON 匯出。

## 線上分享建議

如果要放在 GitHub Pages 給大家自行使用，建議上傳或覆蓋這個檔案：

```text
旅遊規劃系統.html
```

這是已打包好的單檔版，CSS 與 JavaScript 都已內嵌，不需要另外上傳 `src/` 或 `assets/` 才能運作。

GitHub Pages 網址通常會是：

```text
https://你的帳號.github.io/你的儲存庫名稱/旅遊規劃系統.html
```

如果儲存庫名稱是 `-`，網址會類似：

```text
https://zhanhung69-tech.github.io/-/旅遊規劃系統.html
```

也可以在 GitHub 右側的 `Deployments` 或 `Settings > Pages` 查看實際網址。

## 更新分享版

如果有修改 `index.html`、`src/` 或 `assets/`，請先在本機執行：

```bash
node build_share_html.js
```

它會重新產生：

```text
旅遊規劃系統.html
```

再把新的 `旅遊規劃系統.html` 上傳到 GitHub。

## 使用者資料與備份

本系統採本機瀏覽器儲存：

- 每個使用者的行程資料只會存在自己的手機/電腦瀏覽器。
- 其他人打開同一個 GitHub Pages 網址，不會看到你的行程。
- 清除瀏覽器資料、換手機、換瀏覽器，原本行程可能不見。

建議使用者在重要行程完成後，到系統內：

```text
匯出 / 同步 > 旅程紀錄檔（備份 / 還原）> 下載紀錄檔
```

需要換裝置時，再用「匯入 / 還原」載入 JSON 備份。

重要提醒：不要把個人的 JSON 備份、共編包、收據照片或含私人資訊的檔案上傳到公開 GitHub。

## GitHub 上傳方式

最簡單方式：

1. 進入 GitHub 儲存庫。
2. 按 `Add file > Upload files`。
3. 拖曳新的 `旅遊規劃系統.html` 到頁面。
4. Commit message 可填：`Update travel planner shared HTML`。
5. 按 `Commit changes`。
6. 等 GitHub Pages 部署完成後，重新整理分享網址。

若要讓首頁直接打開系統，可另外把 `index.html` 也上傳，或把 `旅遊規劃系統.html` 複製成 `index.html` 後上傳。

## 開發版檔案

目前開發版採拆檔架構：

```text
index.html
assets/styles/app.css
src/config/app-config.js
src/data/catalog.js
src/data/region-catalog.js
src/services/storage-service.js
src/services/sort-plan-service.js
src/app.js
```

開發或測試建議使用本機伺服器開啟：

```bash
python -m http.server 8899
```

再瀏覽：

```text
http://127.0.0.1:8899/index.html
```

## 目前限制

- Google Map 目前是開啟地點/路線搜尋，不是雙向同步修改行程。
- 多人共編目前以 JSON 共編包交換為主，尚未接雲端帳號與即時同步。
- 旅遊資料庫已建立地區分層架構，後續可逐步補齊更多城市、景點、營業時間、票券與交通資料。

