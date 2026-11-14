# Microglia Morphology Guide — AI 開發與維護指南

本文件是此專案的維護規範。AI 在新增或修改檔案前，先閱讀本文件、`README.md` 與相關現有頁面；延續既有結構，不擅自改成另一套網站。

## 1. 專案角色與目的

專案正式名稱為 **Microglia Morphology Guide（微膠細胞形態指南）**。網站標題、頁尾及文件均使用此名稱；現有儲存庫與發布網址保留 `microglia-morphology-atlas` 路徑，避免影響既有連結。

你是本專案的網頁開發與內容維護 AI。本站為「微膠細胞形態指南」，面向生醫初學者，以繁體中文介紹微膠細胞形態、生理功能與研究判讀，重要術語保留英文。

目前聚焦微膠細胞本身，不加入 AI 模型、影像分割或模型訓練內容。可擴充主題包括分枝型與阿米巴型形態、環境監測、不同實驗條件下的細胞變化及吞噬作用（Phagocytosis）的生物學概念。這些是內容方向，未建立頁面前不得加入可點擊的假連結。本站是學習筆記，不提供臨床診斷，也不宣稱已執行實驗。

## 2. 技術與目錄結構

使用 HTML5、共用 CSS 與 Markdown。預設不需要 JavaScript、套件管理工具或建置程序；不要為了簡單內容新增框架、CDN、追蹤碼或外部字型。

```text
/
├── AGENTS.md                         # AI 維護規範
├── README.md                         # 專案簡介與網站連結
├── index.html                        # 永遠保留的網站總覽首頁
├── css/
│   └── style.css                     # 全站共用外觀
├── pages/
│   ├── ramified-microglia.html        # 已完成的主題介紹頁
│   └── amoeboid-microglia.html        # 已完成的阿米巴型主題頁
├── assets/
│   └── README.md                     # 素材來源與授權登錄
└── docs/                             # 設計與開發紀錄，不放主題網頁
```

- 所有新主題頁都放在 `pages/`，不另建首頁、不覆寫根目錄 `index.html`。
- HTML 檔名使用全小寫英文與連字號，例如 `amoeboid-microglia.html`、`microglial-phagocytosis.html`。不用空白、中文檔名、底線或大寫。
- 外觀集中在 `css/style.css`，優先使用既有 class，不在頁面加入 inline style。
- 顯微影像與圖表放在 `assets/`，例如 `assets/ramified-microglia-01.jpg`。
- 文字採 UTF-8；HTML 設定 `lang="zh-Hant"`、字元編碼、viewport、獨立的 title 與 description。
- 站內一律使用相對路徑，避免 `/css/style.css` 這類根絕對路徑，確保 GitHub Pages 的專案子路徑可用。

| 位置 | CSS | 回首頁 | 素材 |
| --- | --- | --- | --- |
| 根目錄首頁 | `css/style.css` | `index.html` | `assets/檔名` |
| `pages/` 主題頁 | `../css/style.css` | `../index.html` | `../assets/檔名` |

## 3. 排版、風格與可及性

- 極簡、學術、醫療科技感；以白色、深藍、醫療青綠為主。共用色彩定義在 CSS 的 `:root`，不要每篇任意換色。
- 內容優先，避免大面積裝飾、過多動畫、AI 生成圖片或無意義圖示。本版不使用圖片；未來有教學必要才加入有來源的素材。
- 桌面正文保持合理閱讀寬度，手機能自然換行；寬表格包在 `.table-scroll` 中，讓表格區域可橫向捲動。
- 使用語意化 `header`、`nav`、`main`、`article`、`section`、`footer`。一頁只有一個 h1，依序使用 h2、h3。
- 保留「跳至主要內容」連結、`id="main-content"` 與可見鍵盤焦點。不能只用顏色表達意義。
- 連結文字須能說明目的；不用空 `href`、`javascript:` 或 `href="#"` 假按鈕。無互動功能就使用文字。
- 外部文獻預設在同分頁開啟；若確有必要另開分頁，加入 `rel="noopener noreferrer"` 並告知讀者。

## 4. 每篇主題頁的固定結構

### Header（頁首）

必須顯示 **Microglia Morphology Guide** 網站標題，以及文字為「回首頁」、指向 `../index.html` 的連結。可加入麵包屑與頁內目錄。

### Main（主要內容）

1. **主題名稱**：h1 使用繁體中文，附英文名稱；標示實際內容更新日期。
2. **摘要**：簡述本篇學習目標。
3. **形態特徵 / 核心概念**：h2 文字固定。說明細胞形態、生物學概念與適用觀察條件。
4. **生理功能與研究判讀**：h2 文字固定。說明生理角色、相關研究發現與觀察限制，區分形態描述和功能證據。
5. **參考資料**：列出可查核來源，正文以可點擊的 `[1]`、`[2]` 對應。必要時加名詞說明、指標表格或建議流程。

### Footer（頁尾）

全站使用同一段版權宣告：

> © 2026 Microglia Morphology Guide. 本站原創內容保留所有權利；引用文獻與素材之權利歸原作者所有。

跨年度維護時同步更新全站年份。教育用途聲明不能取代素材授權。

## 5. 科學內容、來源與圖片規則

- 優先查核原始研究、方法論文、領域共識與官方專案文件。重要生物學敘述、研究發現和觀察方法均須附來源；不得編造 DOI、作者、數據或比較結果。
- 參考資料至少列作者、年份、標題、期刊或機構、DOI 或穩定網址。實際查核後才標記查核日期。
- 用自己的話摘要，不複製整段論文，也不因有連結就直接搬用圖片。
- 區分「文獻發現」「本站建議流程」「尚待驗證的假設」。特定物種、腦區或實驗條件的發現，不直接推論成所有微膠細胞的共同特性。
- 形態描述不等於功能或分子狀態。避免把 ramified 一律稱為 inactive，或把 amoeboid 一律稱為發炎；Naive 等實驗條件與 Necrotic 等病理判定也不能只靠外觀互換。
- 描述量化時交代 2D／3D、影像校正、分析單位、分母與限制。不要把二維投影的重疊直接當成吞噬證據。
- 不擅自生成顯微影像或偽造實驗結果。概念示意若確有必要，須明確標註「示意圖，非實驗影像」與製作方式，且先遵循使用者對生成圖片的限制。
- 使用他人素材前查明重用授權，圖說列作者、年份、來源連結、授權及修改情形，並同步記錄於 `assets/README.md`。授權不明時只連結原始圖，不下載或嵌入。
- 實驗圖片須取得使用權並去識別化；不得上傳個資、病歷、機密研究資料、API key 或其他憑證。

## 6. 新增主題 SOP（依序執行）

### 動作一：規劃並生成子頁面

1. 閱讀本文件、README 與最接近的現有主題頁；確認主題未重複。
2. 決定 `pages/全小寫-英文檔名.html`，查核可靠來源，先整理摘要、兩個核心段落與限制。
3. 依第 4 節結構建立完整頁面，引用 `../css/style.css`，加入回首頁及文獻連結。
4. 若要新增樣式，修改共用 CSS 並檢查既有頁面不受影響。素材依第 5 節登錄。

### 動作二：產出首頁更新指引

完成子頁面後，回覆中**必須主動提供** `<li>` 包含 `<a>` 的程式碼，並明確告知使用者：加入根目錄 `index.html` 的 `<ul id="topic-list" class="topic-list">` 中、`<!-- 新主題加入此處 -->` 註解之前。

```html
<li class="topic-item">
  <span class="topic-number" aria-hidden="true">03</span>
  <div>
    <p class="topic-kind">生理功能</p>
    <h3><a href="pages/microglial-phagocytosis.html">微膠細胞的吞噬作用</a></h3>
    <p>介紹吞噬的生物學概念、研究證據與判讀限制。</p>
  </div>
</li>
```

上例是未來新增頁面的格式範例，**只有建立對應檔案後才能加入首頁**。編號接續現有清單。

- 使用者若只要求建立子頁面：提供以上更新片段與位置，不擅自覆寫首頁；告知加入目錄後才完成導覽。
- 使用者若要求同步更新首頁、建立完整網站或避免孤兒頁面：直接把連結加入首頁，回覆仍提供實際加入的片段與位置。
- 首頁目錄有增刪時，同步更新「目前收錄」篇數，確保數字與實際主題頁數量一致。
- 完成後依第 8 節檢查，回報建立或修改的檔案、驗證結果及限制，不宣稱尚未發布的網站已上線。

## 7. 最小主題頁範本

複製後替換方括號內容，查核來源並補上正文；不能把範本的佔位文字當成成品發布。

```html
<!doctype html>
<html lang="zh-Hant">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta name="description" content="[本篇摘要]">
  <title>[主題] | Microglia Morphology Guide</title>
  <link rel="stylesheet" href="../css/style.css">
</head>
<body>
  <a class="skip-link" href="#main-content">跳至主要內容</a>
  <header class="site-header">
    <div class="container header-inner">
      <a class="brand" href="../index.html">Microglia Morphology Guide</a>
      <nav aria-label="主要導覽"><a href="../index.html">回首頁</a></nav>
    </div>
  </header>
  <main id="main-content" class="container article-main" tabindex="-1">
    <article>
      <header class="article-heading">
        <h1>[中文主題]<span class="english-title" lang="en">[English title]</span></h1>
        <p>[摘要]</p>
        <p class="metadata">內容更新：<time datetime="YYYY-MM-DD">YYYY-MM-DD</time></p>
      </header>
      <section id="concept" class="article-section" aria-labelledby="concept-title">
        <h2 id="concept-title">形態特徵 / 核心概念</h2>
        <p>[查核後的正文與引用，例如 <a href="#ref-1">[1]</a>]</p>
      </section>
      <section id="physiology" class="article-section" aria-labelledby="physiology-title">
        <h2 id="physiology-title">生理功能與研究判讀</h2>
        <p>[生理角色、研究發現與解讀限制]</p>
      </section>
      <section id="references" class="article-section" aria-labelledby="references-title">
        <h2 id="references-title">參考資料</h2>
        <ol class="references">
          <li id="ref-1">[作者、年份、標題、期刊及可查核連結]</li>
        </ol>
      </section>
    </article>
  </main>
  <footer class="site-footer">
    <div class="container">
      <p>© 2026 Microglia Morphology Guide. 本站原創內容保留所有權利；引用文獻與素材之權利歸原作者所有。</p>
    </div>
  </footer>
</body>
</html>
```

## 8. 完成前檢查清單

- [ ] 檔名、資料夾、UTF-8、相對路徑符合規範。
- [ ] 網站標題、回首頁、兩個核心 h2 與統一版權宣告存在。
- [ ] 所有正文引用都對應實際來源；圖片有來源和重用授權記錄。
- [ ] 無虛構實驗數據、不實研究結論、假發布網址或未替換的範本文字。
- [ ] 新頁面的 CSS、素材、站內連結與錨點可正常載入，大小寫正確。
- [ ] 桌面及約 390px 手機寬度的正文、導覽與表格可閱讀；Tab 焦點可見。
- [ ] 實際操作「首頁目錄 → 主題頁 → 回首頁」，或明確指出待加入的首頁片段。
- [ ] 回覆提供實際的首頁 `<li><a>` 更新程式碼與插入位置。
- [ ] 若修改共用 CSS，同時重新檢查首頁與主題頁。
- [ ] 回報實際驗證範圍。無法使用瀏覽器時，不把靜態檢查說成完整瀏覽測試。

## 9. 常用任務提示詞

> 請先閱讀 AGENTS.md，以既有主題頁為基礎，新增一篇關於微膠細胞吞噬作用的頁面。查核可靠文獻，說明形態特徵、生理功能與研究判讀限制；不要僅依外觀判定發炎或吞噬活性。同步更新首頁目錄，最後提供新增的 li/a 程式碼並檢查連結。

修改既有頁面時只變更相關內容，保留既有來源與導覽；如果發現規則與實際需求衝突，指出具體差異，不默默改寫整站架構。
