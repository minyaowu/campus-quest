# 空堂冒險 Campus Quest

把課與課之間的空白，變成一場小冒險。

**公開網站：https://minyaowu.github.io/campus-quest/**  
**原始碼：https://github.com/minyaowu/campus-quest**

2026-10-14 已依使用者授權公開，並在真正的 Pages 網址操作驗證篩選、抽卡、接受、開始、暫停／繼續、重新整理復原、取消及手機排版。交作業請使用上方公開網站網址；file:/// 開頭的路徑只能開啟自己電腦上的檔案。

這是一個原生 HTML、CSS、JavaScript 的校園任務抽卡網站，內建 40 個任務。所有執行內容都在根目錄 `index.html`，不需要安裝套件、建置或後端，不載入外部資源。

## 直接開啟
1. 若下載 ZIP，先解壓縮。
2. 用 Chrome、Edge、Firefox 或 Safari 的較新版本開啟 `index.html`，例如在檔案總管雙擊檔案。實際自動化驗收使用本機 Chrome；其他瀏覽器尚待人工確認。
3. 設定時間、最高預算與地點 → 抽一個冒險 → 接受或換一個 → 開始倒數。
4. 需要時暫停／繼續。按「提前完成」或倒數結束後的「確認完成」，再在對話框確認，才會增加完成紀錄。
5. 取消任務及清除紀錄都有確認對話框；按返回或 Escape 不會刪除資料。清除紀錄不影響目前任務。

沒有預先塞入使用者資料或完成紀錄。儲存空間若被瀏覽器禁止，仍可操作，但重新整理後的資料可能無法保留。資料只在目前瀏覽器，沒有帳號、同步或定位；`file://` 與 GitHub Pages、不同路徑或不同瀏覽器的紀錄不保證共用。

## 檔案說明
|檔案|用途|
|---|---|
|index.html|唯一必需的網站執行檔，內嵌樣式、程式、SVG 與全部任務|
|SPEC.md|開發前規格及驗收版更新|
|AI-ITERATIONS.md|真實三階段工作、觀察、調整與工具限制|
|TEST-REPORT.md|F01～F06 的預期／實際結果與待確認項目|
|SUBMISSION.md|可以直接複製到作業文字區的完整草稿|
|screenshots/|實際執行作品的桌機、手機、進行、暫停與完成展示截圖|
|test-evidence/|此次核心、瀏覽器與最後檢查的原始 JSON 證據（網站不依賴）|

開發中的主檔案在原專案根目錄。`outputs/Campus-Quest/` 與 `outputs/Campus-Quest.zip` 是交付副本；上傳 GitHub 時，把副本**裡面的內容**放到儲存庫根目錄，而不是把整個 outputs 或 Campus-Quest 外層資料夾上傳。

## GitHub Pages 部署
本專案已部署於 `minyaowu/campus-quest`，發布來源為 `main` 分支的 `/(root)`。以下保留可重現的 GitHub 網頁上傳方式，不需要本機 GitHub CLI。

1. 登入自己的 GitHub，建立或選擇自己有管理權限的目標儲存庫；不要改動無關儲存庫。若採 GitHub Free，可使用公開儲存庫。
2. 在目標儲存庫使用 **Add file → Upload files**，把本專案的 `index.html` 放在根目錄。可一起上傳規格、README、修改紀錄、測試報告與 screenshots。先檢查沒有覆蓋目標儲存庫內的無關同名檔案。
3. 提交到你選定的分支（例如實際存在的 `main`；不要猜測分支名稱）。
4. 開啟 **Settings → Pages → Build and deployment**，Source 選 **Deploy from a branch**。
5. Branch 選擇剛才包含根目錄 `index.html` 的分支，資料夾選 **/(root)**，按 **Save**。這個專案不用選 `/docs`，也不需要 npm 或 GitHub Actions 自訂建置流程。
6. 等待 Pages 工作流程成功，從 Pages 設定頁取得實際網址。一般專案網址形如 `https://[帳號].github.io/[儲存庫]/`，這裡只是格式，不是已公開的網址。
7. 開啟實際網址，驗證 5 分鐘／0 元／室內 → 抽卡 → 接受 → 開始 → 暫停；再重新整理檢查復原。檢查 DevTools Console、手機排版與 Network。
8. 把已驗證的網址填入 SUBMISSION.md，依老師要求上傳截圖。若想以公開網址為截圖證据，可在部署後重新擷取相同畫面。

步驟依 [GitHub 官方發布來源文件](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site) 與 [Pages 建站文件](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site) 核對（2026-10-13）。網站沒有絕對根路徑資源，已在本機 `/campus-quest/` 子路徑執行驗證。

本次部署：使用者提供帳號 minyaowu，同意建立並公開 campus-quest，並自行登入 GitHub。AI 透過已登入的瀏覽器上傳已驗收的單一 index.html，設定 Pages 為 main／根目錄；沒有取得、保存或要求使用者提供密碼、Token、驗證碼。初次網站提交為 `cc518d8fe15fd087e9eef0c185785edcc9cc57de`。

## 測試與截圖
本次完成 11 組核心邏輯測試、23 項 Chrome 瀏覽器測試；細節見 TEST-REPORT.md。單候選／零候選及 900ms 逾時計時使用隔離測試資料，重新載入後即丟棄，正式任務庫未因此更改。

截圖說明見 `screenshots/README.md`。完成紀錄截圖是手動確認的測試展示資料，不代表真實完成學習活動，沒有寫入網站檔案的初始狀態。

公開後另擷取 `07-public-main.jpg`、`08-public-active.jpg`、`09-public-mobile.jpg`；這三張來自真正的 Pages 網址，正式任務為「一句話複習」，沒有注入任務或完成紀錄。公開流程證據見 `test-evidence/public-verification.json`。
