# Microglia Morphology Atlas Implementation Plan

> 版本說明（2026-11-14）：下方為初版歷史紀錄。使用者後續已要求聚焦微膠細胞生物學；現行網站與 AGENTS.md 以「形態特徵 / 核心概念」及「生理功能與研究判讀」為核心，移除 AI 模型與影像分割內容。主題頁現有三筆參考資料；目前規範以根目錄 AGENTS.md 為準。

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** 完成可依規則擴充、可由 GitHub Pages 發布的靜態學術知識庫。

**Architecture:** 根目錄首頁、pages/ 主題頁、css/ 共用樣式、assets/ 素材說明。無框架、無 JavaScript、無外部字型或生成圖片。

**Tech Stack:** HTML5、CSS、Markdown。

**Spec:** docs/superpowers/specs/2026-11-14-microglia-atlas-design.md；另遵循使用者最新指定的醫療色系與圖片來源規則。

## Global Constraints
- 保留 index.html；主題頁使用小寫連字號檔名與 ../css/style.css。
- 每頁有 Header、Main、Footer；主題頁包含兩個指定核心段落。
- 不使用 AI 生成圖片；學術敘述提供來源，不捏造數據與發布網址。
- 本次只完成本機專案與部署指引，不執行外部發布。

## Review Focus
- GitHub Pages 專案路徑：所有站內連結使用相對路徑。
- 手機窄螢幕：導覽換行、表格可橫向捲動、正文不溢出。
- 鍵盤操作：跳至主要內容、可見焦點、連結文字可理解。
- 學術誤解：形態不等於功能；建議流程與文獻發現分開標示。
- 可擴充性：規則、主題頁及 README 的目錄名稱與 SOP 一致。

### Task 1: 維護文件與網站
**Files:** AGENTS.md、index.html、pages/ramified-microglia.html、css/style.css、assets/README.md、README.md。
- [x] 撰寫具體的維護規則、範本與檢查清單。
- [x] 依原始文獻撰寫主題頁，實作首頁及共用響應式 CSS。
- [x] 補上發布、繳交與新增頁面指引。

### Task 2: 驗證與交付
- [x] 以 HTML parser 檢查本機路徑、錨點、必要結構與主題目錄。
- [ ] 實際瀏覽首頁 → 主題頁 → 回首頁，檢查桌面及窄版排版。（瀏覽器權限審核拒絕，不繞過限制。）
- [x] 核對來源、版權與部署限制，回報實際完成項目。

## Execution notes
- 全新資料夾無 Git 儲存庫；直接在使用者指定的工作區建立檔案，不建立 worktree 或自行提交。
- 依上層規則，這次純靜態內容與樣式不建立單元測試套件，採結構、連結與瀏覽器驗證。
- 使用者已授權依確認設計直接製作，計畫不另設確認關卡。
- 靜態驗證：兩頁 HTML 標籤配對、唯一 h1、無重複 ID、33 個本機路徑與錨點通過；主題頁兩個指定 h2 與四筆引用存在。
- 主要文字色彩對比計算：5.39:1、5.97:1、11.32:1、9.06:1，均高於 4.5:1。此計算不等於完整可及性稽核。
- 驗證腳本第一次因 Windows PowerShell 傳入 Python 的中文字串轉成問號而中止；確認檔案 UTF-8 正常後，以 Unicode escape 重跑，全部靜態檢查通過。未因此修改網頁內容。
- 獨立程式碼審查：未發現需修正的重要問題；審查不含外部文獻重查與瀏覽器實測。
- 本次無 AI 生成圖片，也未部署或建立 GitHub Repository。尚待允許的瀏覽器環境進行桌面、手機及鍵盤操作驗證。
