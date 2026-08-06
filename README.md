# Yu-Xiang Zhao 個人網站

靜態學術個人網站（Static Academic Homepage），以純 HTML + CSS 撰寫，不需要任何建置工具、套件管理器或伺服器即可直接瀏覽。

- 作者：趙于翔（Yu-Xiang Zhao）
- 服務單位：國立金門大學 資訊工程學系
- 語言：繁體中文（個人簡介含英文說明）
- Doctype：XHTML 1.0 Strict
- 版面設計改編自 "astroturfd" Free CSS Templates（CC Attribution 2.5）

## 頁面

| 頁面 | 內容 |
| ---- | ---- |
| `index.html` | 個人簡介（Bio / 學歷 / 經歷 / 研究興趣） |
| `publications.html` | 期刊與研討會論文 |
| `courses.html` | 歷年授課進度大綱（97 學年度至今） |
| `students.html` | 指導學生論文與專題成果 |

所有頁面共用 `style.css`，並以 `.section-card` 區塊呈現內容。

## 資料夾結構

```
courses/  授課進度大綱 PDF，檔名格式 <學期>_<課程代碼>.pdf
students/ 論文 / 專題成果（PDF、JPG、MP4）
images/   個人照片與 favicon
```

## 在本機預覽

直接用瀏覽器開啟 `index.html` 即可，或在本目錄執行：

```bash
python -m http.server 8000
```

然後瀏覽 `http://localhost:8000`。

## 部署到 GitHub Pages

1. 將本專案推送到 GitHub 倉庫（公開倉庫）。
2. 在 GitHub 倉庫頁面選擇 **Settings → Pages**。
3. **Source** 選 **Deploy from a branch**，Branch 選 `main`，資料夾選 `/ (root)`。
4. 儲存後稍等幾分鐘，即可透過 `https://<你的帳號>.github.io/<倉庫名稱>/` 存取。

## 授權

- 網站內容與照片版權屬於 Yu-Xiang Zhao。
- 版面設計基於 astroturfd 模板，依 CC Attribution 2.5 授權使用。
