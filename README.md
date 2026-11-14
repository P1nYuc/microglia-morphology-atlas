# Microglia Morphology Atlas

[公開網站](https://p1nyuc.github.io/microglia-morphology-atlas/) · [GitHub Repository](https://github.com/P1nYuc/microglia-morphology-atlas)

微膠細胞形態與生理知識庫。以繁體中文介紹形態特徵、生理功能與研究判讀，並透過 [AGENTS.md](AGENTS.md) 建立可重複使用的 AI 維護流程。

網站採醫療常見的深藍、青綠與白色，以文字、表格及學術引用為主；目前沒有 AI 生成圖片、實驗影像或外部字型。

## 專案成果

- **首頁：** [index.html](index.html)，包含專案介紹、主題目錄、知識庫範圍及閱讀指南。
- **主題介紹：** [分枝型微膠細胞 Ramified Microglia](pages/ramified-microglia.html)，包含兩個固定核心段落、生理角色、觀察限制與三筆參考文獻。
- **主題介紹：** [阿米巴型微膠細胞 Amoeboid Microglia](pages/amoeboid-microglia.html)，介紹形態特徵、生理功能與判讀限制，附三筆可靠文獻。
- **維護規則：** [AGENTS.md](AGENTS.md)，包含目錄、命名、來源、素材授權、HTML 範本、新增主題 SOP 及完成檢查清單。
- **共用樣式：** [css/style.css](css/style.css)，支援桌面、手機與鍵盤操作。
- **素材登錄：** [assets/README.md](assets/README.md)，供後續新增有來源及授權的圖片。

本專案是學習與研究筆記，目前聚焦微膠細胞本身的生物學知識；不作為臨床診斷依據。形態分類不直接等同於功能或分子狀態。

## 檔案結構

```text
Microglia Morphology Atlas/
├── AGENTS.md
├── README.md
├── index.html
├── css/
│   └── style.css
├── pages/
│   ├── ramified-microglia.html
│   └── amoeboid-microglia.html
├── assets/
│   └── README.md
└── docs/superpowers/
    ├── specs/                  # 設計紀錄
    └── plans/                 # 開發與驗證紀錄
```

## 在自己的電腦上瀏覽

直接用瀏覽器開啟根目錄 `index.html` 即可。本站不需要安裝套件、API key 或執行建置。

也可以在專案根目錄開啟終端機，使用已安裝的 Python 啟動本機伺服器：

```powershell
python -m http.server 8000 --bind 127.0.0.1
```

開啟 [本機首頁](http://127.0.0.1:8000/)，用 `Ctrl+C` 停止伺服器。若 8000 已被使用，改用另一個埠號並同步修改網址。本機網址只供自己預覽，不能作為作業的公開網站網址。

## 上傳 GitHub 並啟用 GitHub Pages

**目前狀態：** 專案已上傳至 [GitHub Repository](https://github.com/P1nYuc/microglia-morphology-atlas)，GitHub Pages 已啟用，發布來源為 `main` 分支的 `/ (root)`，並啟用 HTTPS。[公開網站](https://p1nyuc.github.io/microglia-morphology-atlas/)的首頁、兩篇主題頁、CSS 與 AGENTS.md 已確認可透過公開網址讀取。

以下保留首次部署步驟作為維護參考；目前專案不需要重新建立儲存庫或初始化 Git。

### 1. 建立並上傳儲存庫

在 GitHub 建立公開 Repository，建議名稱 `microglia-morphology-atlas`。若使用以下指令上傳，建立時先不要勾選自動加入 README、LICENSE 或 .gitignore，避免和本機檔案衝突。

在專案根目錄執行下列指令。**先將 `YOUR-USERNAME` 替換成自己的 GitHub 帳號**，並確認 Repository 名稱相符；登入驗證交由 GitHub 或 Git Credential Manager 處理，不把 token 寫進檔案。

```powershell
git init
git add AGENTS.md README.md index.html css pages assets docs
git commit -m "Create Microglia Morphology Atlas"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/microglia-morphology-atlas.git
git push -u origin main
```

以上適用於全新儲存庫；如果專案已有 Git 記錄或 origin，先檢查現況，不要重複初始化或覆寫遠端設定。也可透過 GitHub 網站的 **Add file → Upload files** 上傳檔案與資料夾，保留目錄結構。`index.html` 必須位在 Repository 根目錄，不能多包一層資料夾。

### 2. 公開網站

1. 打開 Repository 的 **Settings → Pages**。
2. 在 **Build and deployment → Source** 選 **Deploy from a branch**。
3. 選擇 **main** 分支與 **/ (root)** 資料夾，按 **Save**。
4. 等待部署完成；可在 **Actions** 查看執行結果，再回 Pages 複製實際網站網址。
5. 用公開網址檢查「首頁 → 主題介紹 → 回首頁」，並確認手機版與 CSS 正常。

專案網站的網址通常是 `https://YOUR-USERNAME.github.io/microglia-morphology-atlas/`，但**請以 Pages 顯示的實際網址為準**。初次發布可能需要幾分鐘；若 404，檢查部署是否完成、發布來源及根目錄是否有 `index.html`。若樣式遺失，檢查相對路徑和檔名大小寫。

上述方式依據 [GitHub Pages 官方發布來源說明](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)；免費帳號可使用公開儲存庫發布，見 [GitHub Pages Quickstart](https://docs.github.com/en/pages/quickstart)。

## 讓 AI 繼續新增一篇內容

範例提示詞：

> 請先閱讀 AGENTS.md 與目前的主題頁。新增一篇關於微膠細胞吞噬作用的主題頁，使用繁體中文並保留英文術語。查核可靠文獻，包含「形態特徵 / 核心概念」及「生理功能與研究判讀」。不要僅憑形態判定功能，也不要使用生成圖片。同步更新首頁目錄，提供新增的 li/a 程式碼與插入位置，並驗證頁面及回首頁連結。

AI 應依序完成：

1. 查閱規範與來源，決定全小寫、連字號檔名，例如 `pages/microglial-phagocytosis.html`。
2. 沿用固定頁面結構與 `../css/style.css`，補上參考資料、回首頁與統一頁尾。
3. 依提示詞授權同步更新首頁；如果只要求子頁面，則提供目錄片段與插入指引。
4. 檢查連結、引用、手機排版和鍵盤操作，回報實際驗證結果。

每次新增主題，都在根目錄 `index.html` 的 `<ul id="topic-list" class="topic-list">` 內、`<!-- 新主題加入此處 -->` 註解前加入目錄項目，並更新「目前收錄」篇數。只有已建立的頁面才能加入連結。

分枝型微膠細胞介紹頁已加入首頁，其對應片段如下，**不用重複貼上**：

```html
<li class="topic-item">
  <span class="topic-number" aria-hidden="true">01</span>
  <div>
    <p class="topic-kind">細胞形態</p>
    <h3><a href="pages/ramified-microglia.html">分枝型微膠細胞 <span lang="en">Ramified Microglia</span><span class="topic-arrow" aria-hidden="true">↗</span></a></h3>
    <p>認識細長突起與分枝結構，理解環境監測、生理意義與形態判讀的限制。</p>
    <p class="topic-meta">形態特徵 / 生理功能 / 觀察限制 / 參考文獻</p>
  </div>
</li>
```

## 作業要求對照

| 作業要求 | 本專案對應成果 |
| --- | --- |
| 決定小專案 | 微膠細胞形態與生理知識庫 |
| 建立可理解、可延伸的規則 | AGENTS.md 的檔名、結構、來源、範本及 SOP |
| 至少一個可瀏覽網頁 | 首頁、分枝型與阿米巴型微膠細胞介紹頁 |
| GitHub Repository | [P1nYuc/microglia-morphology-atlas](https://github.com/P1nYuc/microglia-morphology-atlas) |
| 公開網站 | [Microglia Morphology Atlas](https://p1nyuc.github.io/microglia-morphology-atlas/) |
| 說明如何持續新增內容 | 上方提示詞與下方繳交說明 |

## 繳交內容範本

以下連結已填入本專案的實際網址；標題中的學校、學號、系級與姓名仍須由本人確認、替換。

**標題：** [學校] [學號] [系級] [姓名] Microglia Morphology Atlas

**1. 專案簡介**

我建立「Microglia Morphology Atlas」，用於整理微膠細胞的形態特徵、生理功能與研究判讀。網站以醫療常用的深藍、青綠與白色呈現，採用靜態 HTML 與共用 CSS，提供首頁、主題目錄，以及分枝型與阿米巴型微膠細胞介紹頁。學術內容附有文獻來源，並區分形態描述與功能判定。

**2. GitHub Repository 連結：** [P1nYuc/microglia-morphology-atlas](https://github.com/P1nYuc/microglia-morphology-atlas)

**3. 網頁連結：** [Microglia Morphology Atlas](https://p1nyuc.github.io/microglia-morphology-atlas/)

**4. AGENTS.md：** [專案維護規範](https://github.com/P1nYuc/microglia-morphology-atlas/blob/main/AGENTS.md)；若課程要求全文，另附全文。

**5. 規則如何協助 AI 繼續擴充？**

我在 AGENTS.md 規定目錄、檔名、共用樣式、固定內容段落及引用方式，並提供完整 HTML 範本和檢查清單。之後只需指定新主題，AI 就能查核資料，在 pages/ 建立符合規範的頁面，再依 SOP 提供首頁目錄的 li/a 更新程式碼。若同時要求更新首頁，AI 會直接加入連結，讓新內容沿用相同風格與導覽結構，降低每次重新說明和遺漏連結的機會。

## 發布及繳交前檢查

- [ ] 個人閱讀並確認學術內容；確保能說明自己的設計。
- [ ] GitHub 上能看見根目錄 AGENTS.md、README.md、index.html 與所有子目錄。
- [ ] 公開網址可在未登入的瀏覽器中載入。
- [ ] 首頁 → 主題頁 → 回首頁的連結與 CSS 正常。
- [ ] 手機上可閱讀正文、頁內目錄及橫向表格。
- [ ] 所有引用可找到對應資料，無未授權圖片或機密資料。
- [ ] 完成繳交標題、Repository、網站及 AGENTS.md 的實際連結。

## 版權與來源

© 2026 Microglia Morphology Atlas. 本站原創內容保留所有權利；引用文獻與素材之權利歸原作者所有。

生物學與觀察方法來源列於[主題頁參考資料](pages/ramified-microglia.html#references)。本站僅提供自行撰寫的導讀，沒有重製論文圖片；未來素材須登錄在 assets/README.md。
