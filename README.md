# HLS Stream Player

<nav>
  <a href="#english">English</a> |
  <a href="#traditional-chinese">繁體中文</a> |
  <a href="#simplified-chinese">简体中文</a>
</nav>

<a id="english"></a>
## English

### Overview

`hls-stream-player` is a single-page browser application for retrieving, selecting, and playing RTHK live HLS streams. It is delivered as a standalone `index.html` file and does not require a build step.

### Features

- Multilingual interface: English, Traditional Chinese, and Simplified Chinese.
- Language preference persisted in browser `localStorage`.
- RTHK live-stream retrieval with a known-stream fallback catalog.
- HLS playback through [hls.js 1.6.2](https://cdn.jsdelivr.net/npm/hls.js@1.6.2/dist/hls.min.js), with native HLS fallback where supported.
- Collapsible player area with live status feedback.
- Playlist selection, reordering, removal, CSV import, and CSV export.
- Copy the selected HLS playlist URL to the clipboard.
- Responsive layout for desktop and mobile browsers.

### Project structure

```text
hls-stream-player/
├── index.html
├── README.md
├── rthk-streams-full.csv
└── rthk-streams-selected.csv
```

### Run locally

From the parent directory, start a local static server:

```powershell
python -m http.server 8765
```

Open [http://localhost:8765/hls-stream-player/](http://localhost:8765/hls-stream-player/) in a modern browser.

### Usage

1. Select a language from the language selector.
2. Select **Get all RTHK streams** to retrieve the current playlist.
3. Choose a stream from the selector.
4. Select **Play stream** or **Start playback**.
5. Use **Edit playlist** to reorder or remove entries.
6. Use **Import** or **Export** to manage a CSV playlist with `name,url` columns.

### Data sources and dependencies

- RTHK live playlist endpoint: <https://programme.rthk.hk/channel/radio/player_live_txt.php>
- CORS fallback proxy: <https://api.allorigins.win/raw?url=>
- HLS.js CDN: <https://cdn.jsdelivr.net/npm/hls.js@1.6.2/dist/hls.min.js>

### Limitations

- Playback depends on browser HLS support, network access, and stream availability.
- If the RTHK endpoint does not allow direct browser access, the app uses the configured CORS fallback proxy.
- RTHK DAB 31, DAB 33, and DAB 35 are treated as unavailable when their published HLS endpoints return HTTP 404.
- The app runs locally in the browser and does not store stream data on a server.

### Verification checklist

- [x] `index.html` loads as a standalone SPA.
- [x] English, Traditional Chinese, and Simplified Chinese translations are included.
- [x] Language switching updates static labels and runtime messages.
- [x] Language preference is persisted locally.
- [x] JavaScript syntax was checked successfully.
- [x] All three language modes were tested in a browser.

<a id="traditional-chinese"></a>
## 繁體中文

### 概覽

`hls-stream-player` 是一個單頁瀏覽器應用程式，用於取得、選擇及播放港台直播 HLS 串流。網站以獨立的 `index.html` 檔案提供，不需要建置步驟。

### 功能

- 多語言介面：English、繁體中文及简体中文。
- 使用瀏覽器 `localStorage` 儲存語言偏好。
- 取得港台直播串流，並在取得失敗時使用已知串流目錄作後備。
- 透過 [hls.js 1.6.2](https://cdn.jsdelivr.net/npm/hls.js@1.6.2/dist/hls.min.js) 播放 HLS，並在支援的瀏覽器中使用原生 HLS 作後備。
- 可收合的播放器區域及即時狀態提示。
- 播放清單選擇、排序、移除、CSV 匯入及 CSV 匯出。
- 將所選 HLS 播放清單網址複製到剪貼簿。
- 適用於桌面及流動瀏覽器的響應式版面。

### 專案結構

```text
hls-stream-player/
├── index.html
├── README.md
├── rthk-streams-full.csv
└── rthk-streams-selected.csv
```

### 本機執行

在父資料夾中啟動本機靜態伺服器：

```powershell
python -m http.server 8765
```

在現代瀏覽器開啟 [http://localhost:8765/hls-stream-player/](http://localhost:8765/hls-stream-player/)。

### 使用方法

1. 在語言選擇器中選擇語言。
2. 選擇「取得所有港台串流」以取得目前播放清單。
3. 從選擇器中選擇串流。
4. 選擇「播放串流」或「開始播放」。
5. 使用「編輯播放清單」排序或移除項目。
6. 使用「匯入」或「匯出」管理包含 `name,url` 欄位的 CSV 播放清單。

### 資料來源及依賴項目

- 港台直播播放清單端點：<https://programme.rthk.hk/channel/radio/player_live_txt.php>
- CORS 後備代理伺服器：<https://api.allorigins.win/raw?url=>
- HLS.js CDN：<https://cdn.jsdelivr.net/npm/hls.js@1.6.2/dist/hls.min.js>

### 限制

- 播放能力取決於瀏覽器的 HLS 支援、網絡連線及串流是否可用。
- 如果港台端點不允許瀏覽器直接存取，應用程式會使用設定的 CORS 後備代理伺服器。
- 當港台 DAB 31、DAB 33 及 DAB 35 的已發佈 HLS 端點回傳 HTTP 404 時，應用程式會將它們視為無法使用。
- 應用程式在瀏覽器本機執行，不會在伺服器儲存串流資料。

### 驗證清單

- [x] `index.html` 可作為獨立 SPA 載入。
- [x] 已包含 English、繁體中文及简体中文翻譯。
- [x] 語言切換會更新靜態標籤及執行時訊息。
- [x] 語言偏好會儲存在本機。
- [x] JavaScript 語法檢查成功。
- [x] 已在瀏覽器測試三種語言模式。

<a id="simplified-chinese"></a>
## 简体中文

### 概览

`hls-stream-player` 是一个单页浏览器应用，用于获取、选择和播放港台直播 HLS 流。网站以独立的 `index.html` 文件提供，不需要构建步骤。

### 功能

- 多语言界面：English、繁體中文和简体中文。
- 使用浏览器 `localStorage` 保存语言偏好。
- 获取港台直播流，并在获取失败时使用已知流目录作为备用。
- 通过 [hls.js 1.6.2](https://cdn.jsdelivr.net/npm/hls.js@1.6.2/dist/hls.min.js) 播放 HLS，并在支持的浏览器中使用原生 HLS 作为备用。
- 可收起的播放器区域和实时状态提示。
- 播放列表选择、排序、移除、CSV 导入和 CSV 导出。
- 将所选 HLS 播放列表网址复制到剪贴板。
- 适用于桌面和移动浏览器的响应式布局。

### 项目结构

```text
hls-stream-player/
├── index.html
├── README.md
├── rthk-streams-full.csv
└── rthk-streams-selected.csv
```

### 本地运行

在父目录中启动本地静态服务器：

```powershell
python -m http.server 8765
```

在现代浏览器中打开 [http://localhost:8765/hls-stream-player/](http://localhost:8765/hls-stream-player/)。

### 使用方法

1. 在语言选择器中选择语言。
2. 选择“获取所有港台流”以获取当前播放列表。
3. 从选择器中选择流。
4. 选择“播放流”或“开始播放”。
5. 使用“编辑播放列表”对项目进行排序或移除。
6. 使用“导入”或“导出”管理包含 `name,url` 字段的 CSV 播放列表。

### 数据来源和依赖项

- 港台直播播放列表端点：<https://programme.rthk.hk/channel/radio/player_live_txt.php>
- CORS 备用代理服务器：<https://api.allorigins.win/raw?url=>
- HLS.js CDN：<https://cdn.jsdelivr.net/npm/hls.js@1.6.2/dist/hls.min.js>

### 限制

- 播放能力取决于浏览器的 HLS 支持、网络连接和流是否可用。
- 如果港台端点不允许浏览器直接访问，应用会使用配置的 CORS 备用代理服务器。
- 当港台 DAB 31、DAB 33 和 DAB 35 的已发布 HLS 端点返回 HTTP 404 时，应用会将它们视为不可用。
- 应用在浏览器本地运行，不会在服务器存储流数据。

### 验证清单

- [x] `index.html` 可以作为独立 SPA 加载。
- [x] 已包含 English、繁體中文和简体中文翻译。
- [x] 语言切换会更新静态标签和运行时消息。
- [x] 语言偏好会保存在本地。
- [x] JavaScript 语法检查成功。
- [x] 已在浏览器中测试三种语言模式。
