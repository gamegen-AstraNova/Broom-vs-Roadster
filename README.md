# Broom vs Roadster

GameGen 可直接遊玩的網頁交付版本（HTML ZIP 直接上傳模式，不換皮）：女版馬份騎光輪 2001，對上二次元版馬斯克的飛天 Roadster，社群分享用的同人小遊戲（非商用）。根目錄是已建置的 React 19 + Three.js 遊戲，含 9:16 封面。

## 線上遊玩

[Play Broom vs Roadster](https://gamegen-astranova.github.io/Broom-vs-Roadster/)

## 操作

- W 或 ↑：掃帚按住爬升；飛天車推進器跳躍
- 空白鍵：加速（加速中可撞破障礙）
- P 或 Esc：暫停

## 本地預覽

在本目錄執行 `python -m http.server 8000`，瀏覽 `http://localhost:8000/`。請用 HTTP 服務載入設定與資產，不要以 `file://` 直接開啟 `index.html`。

## GameGen 打包

在本目錄執行 PowerShell：

```powershell
Compress-Archive -Path index.html,poster.webp,assets,common,config -DestinationPath ../broom-vs-roadster.zip -Force
```

將 `broom-vs-roadster.zip` 上傳後台。ZIP 根目錄須直接包含 `index.html`、`poster.webp`、`assets/`、`common/`、`config/`，不可再包一層目錄。專案及 ZIP 名稱只保留遊戲名稱，不添加 noskin 或 html 後綴。

## 檔案

- `index.html`：已建置入口。
- `assets/`：已編譯的 JS 與 CSS。
- `common/textures/`（WebP）、`common/audio/`、`common/fonts/`：遊戲圖片、音訊與四語字型子集；資源清單在 `config/asset-manifest.json`。
- `config/language/`：英文、繁體中文、簡體中文、日文；預設英文。
- `config/generalConfiguration.json`：載入設定；這個版本使用包內資產。
- `poster.webp`：936 × 1664、9:16 無損 WebP 平台封面，不加入遊戲內資產表。

此儲存庫只放建置產物，不含 React／TypeScript 原始碼與開發用的美術原圖、審閱影片；那些在團隊的 broom-vs-roadster 專案（其 README.md、HANDOFF.md 記錄做法與每次的決定）。

## 驗證

2026-10-21：交付 ZIP 解壓到 HTTP 子路徑實測，217 個資源都從子路徑載入、沒有失敗、主控台沒有錯誤；進入、選角、開賽正常。
