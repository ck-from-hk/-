# 快快快樂學倉頡

![Platform](https://img.shields.io/badge/platform-Web%20%7C%20Offline-005a52)
![Size](https://img.shields.io/badge/size-~100%20KB%20HTML-informational)
![License](https://img.shields.io/badge/license-MIT-green)
![Engine](https://img.shields.io/badge/engine-Vanilla%20JS-000000)

> 九十年代 DOS 打字教學程式致敬之作——單一 HTML 檔，毋須安裝、毋須連網即可完整執行。
> A tribute to 1990s DOS typing tutors — a single HTML file that runs fully offline, no install required.

https://ck-from-hk.github.io/-/
^按此即可遊玩

亦可下載後離線使用
字庫和詞庫可用generator2.html生成

[繁體中文](#繁體中文) ｜ [English](#english)

---

## 繁體中文

### 簡介

本作「致敬」九十年代風行之 DOS 打字教學程式（如松崗《快快樂樂》系列），以單一 HTML 檔重構其經典介面與操作邏輯。內建字庫以標準**三代倉頡**為主碼，部分字附容錯碼，並含五代部分字碼；收錄部分成語及香港用語詞彙作為命題題材。程式為純前端實作——無後端、無帳號、無任何資料上傳，離線開啟即可使用。

### 功能特色

| 模組 | 說明 |
|---|---|
| 軟體簡介 | 使用說明、手機開啟方式、字庫擴充指引 |
| 倉頡入門 | 廿四字根速記、取碼五原則、香港用語字速查 |
| 打字練習 | 逐字拆碼練習，即時對錯標示、可隨時反查字碼 |
| 實力測驗 | 電腦命題／自訂命題，計時、速度、準確率統計 |
| 倉頡查碼 | 輸入任何字即顯示主碼與容錯碼 |
| 最佳成績排行榜 | 成績登錄（本機儲存）、匯出碼表 .tt／.js |
| 音效 | DOS 風格按鍵音（Web Audio 合成，無外部音檔） |

其他：手機虛擬鍵盤自動顯示／偵測實體鍵盤自動隱藏、畫面自動縮放、`Z` 萬用鍵支援任意長度模糊比對、重碼候選字自動置頂。

### 所需檔案

| 檔案 | 必需 | 用途 |
|---|---|---|
| `index.html` | ✅ | 主程式（單檔包含全部 HTML／CSS／JS） |
| `chinese_dict.js` | ⬜ 選配 | 外掛字庫：內容為 `window.EXTERNAL_CHINESE_TT="…"（.tt 碼表字串）`，與 HTML 同資料夾即自動載入 |
| `words_dict.js` | ⬜ 選配 | 外掛題庫：內容為 `window.EXTERNAL_WORDS="詞1 詞2 …"` |
| `chinese.tt` | ⬜ 選配 | 純文字碼表（每行「字 碼」，UTF-8 或 Big5）；http(s) 部署時同目錄自動讀取，本機可經「測驗設定」上傳（存入 IndexedDB，選一次永久記住） |
| `.nojekyll` | ⬜ 建議（GitHub Pages） | 空檔案，令 GitHub Pages 跳過 Jekyll 處理，避免 `_` 開頭資源被忽略 |
| `words.txt` / `*.atc` | ⬜ 選配 | 自訂命題題庫純文字檔（一行一詞或整段文章皆可），經「📂 選擇題庫資料夾」一鍵整夾匯入 |
| `limit.js` | ⬜ 建議 | 依此檔設定常用字範圍 |


> 排行榜頁「匯出 .js」可直接把當前生效的字庫（內建＋已載入擴充碼）包裝成 `chinese_dict.js` 下載，連同 HTML 一併分發即可毋須再設定。

### 快速開始

**方式一：本機直接開啟**
將 `index.html`（連同選配檔案）放於同一資料夾，雙擊以瀏覽器開啟即可。

**方式二：部署到 GitHub Pages**
1. 建立新儲存庫（Public）
2. Upload files 上傳 `index.html`（主檔必須命名為 `index.html`）及選配檔案
3. 另建空檔 `.nojekyll`
4. Settings → Pages → Source: *Deploy from a branch* → Branch: `main` / `/ (root)` → Save
5. 約 1–2 分鐘後即可經 `https://<用戶名>.github.io/<儲存庫名>/` 存取

**方式三：Netlify Drop**
登入後將整個資料夾拖至 [netlify.com/drop](https://app.netlify.com/drop)，即得公開網址。

> **iOS 提醒**：從 WhatsApp／Mail／檔案 App 直接點開本檔時，系統 QuickLook 預覽會停用 JavaScript，程式無法操作——此屬 iOS 安全限制。請改以 Safari 開啟部署後的網頁連結，或將檔案傳至電腦以瀏覽器開啟。Android 以 Chrome 開啟本檔即可完整執行。

### 資料儲存與隱私

| 資料 | 位置 | 說明 |
|---|---|---|
| 排行榜成績 | 瀏覽器 `localStorage` | 僅存本機、按 origin 隔離；清除網站資料即消失 |
| 上傳的擴充字庫 | 瀏覽器 `IndexedDB` | 同上 |
| 題庫資料夾內容 | 瀏覽器 `IndexedDB` | 同上 |

程式**不會**向任何伺服器上傳或同步資料；不同裝置／瀏覽器／開啟方式（內建瀏覽器 vs Safari vs file://）的排行榜互不相通。

### 瀏覽器相容

| 環境 | 支援 |
|---|---|
| 桌面 Chrome / Edge / Firefox / Safari（近期版本） | ✅ 完整 |
| Android Chrome | ✅ 完整 |
| iOS Safari（網頁版） | ✅ 完整 |
| iOS QuickLook 預覽（WhatsApp／檔案 App 內直開） | ⚠️ 僅顯示靜態畫面（預覽器停用 JS） |

### References / Credits

- **朱邦復先生** — 倉頡輸入法發明人（1976，原名形意檢字法；1978 年蔣緯國先生命名「倉頡」）。朱先生於 1982 年公開放棄專利權，促成倉頡普及於各大中文系統。本作字庫以三代倉頡為主碼。參考：[維基百科·倉頡輸入法](https://zh.wikipedia.org/wiki/倉頡輸入法)、[維基教科書·倉頡輸入法](https://zh.wikibooks.org/wiki/倉頡輸入法)（取碼規則及版本沿革）
- **松崗《快快樂樂》系列** — 九十年代風行之 DOS 中文電腦教學軟體／叢書（如《快快樂樂學 DOS》），本作介面與選單邏輯之致敬對象
- **emisjerry（簡睿）** — [cj_jerry.txt 倉頡碼表 Gist](https://gist.github.com/emisjerry/7a1e72688bfc4d4b5c0f9f16f1b84424)，程式內建之線上後備碼表來源（http(s) 部署且同目錄無 `chinese.tt` 時自動載入）
- **倉頡之友** — 三代／五代碼表對照參考

### 授權

本專案程式碼以 [MIT License](LICENSE) 釋出。倉頡輸入法本身無版權限制（發明人已公开放弃專利），惟所引第三方碼表請依其原始來源之授權使用。

---

## English

### About

A tribute to the DOS typing tutors popular in the 1990s (such as the *Kuai Kuai Le Le* series by Sunggang), rebuilt as a single HTML file that faithfully recreates the classic interface and interaction logic. The built-in dictionary uses standard **Cangjie 3rd generation (三代倉頡)** codes as primary, with alternative (fault-tolerant) codes for some characters and partial 5th-generation coverage. Idioms and Hong Kong–specific vocabulary are included as test material. The app is pure front-end — no backend, no accounts, no data upload — and works fully offline.

### Features

| Module | Description |
|---|---|
| About | Usage guide, mobile access notes, dictionary extension guide |
| Tutorial | 24 radicals mnemonic, five composition principles, HK-usage quick reference |
| Typing Practice | Character-by-character code composition with instant correct/wrong feedback and on-demand code lookup |
| Exam | Computer-generated or custom word pools, timed, with speed & accuracy stats |
| Code Lookup | Enter any character to see its primary and alternative codes |
| Leaderboard | Local score saving, export code table as `.tt` or `.js` |
| Sound | DOS-style key beeps synthesized via Web Audio (no audio files) |

Also: auto-appearing virtual keyboard on touch devices (auto-hides when a physical keyboard is detected), responsive scaling, wildcard `Z` key with arbitrary-length fuzzy matching, and auto-priority for the target character among duplicate-code candidates.

### Required Files

| File | Required | Purpose |
|---|---|---|
| `index.html` | ✅ | Main program (single file containing all HTML/CSS/JS) |
| `chinese_dict.js` | ⬜ Optional | External dictionary: `window.EXTERNAL_CHINESE_TT="…"` (a `.tt`-format string); auto-loads when placed in the same folder as the HTML |
| `words_dict.js` | ⬜ Optional | External word pool: `window.EXTERNAL_WORDS="word1 word2 …"` |
| `chinese.tt` | ⬜ Optional | Plain-text code table (one "char code" per line, UTF-8 or Big5); auto-fetched when deployed over http(s) in the same directory, or uploaded once via Exam Setup (persisted in IndexedDB) |
| `.nojekyll` | ⬜ Recommended on GitHub Pages | Empty file that tells GitHub Pages to skip Jekyll processing (avoids underscore-prefixed assets being ignored) |
| `words.txt` / `*.atc` | ⬜ Optional | Custom word-pool text files (one word per line, or free-form prose), imported in bulk via "📂 Choose question folder" |

> The "Export .js" button on the Leaderboard page wraps the currently active dictionary (built-in + any loaded extensions) into a downloadable `chinese_dict.js`, so distributing it together with the HTML requires no further setup.

### Quick Start

**Option 1: Open locally**
Put `index.html` (plus any optional files) in one folder and open it in a browser.

**Option 2: Deploy to GitHub Pages**
1. Create a new public repository
2. Upload `index.html` (must be named exactly this) plus optional files via *Upload files*
3. Also create an empty `.nojekyll` file
4. Settings → Pages → Source: *Deploy from a branch* → Branch: `main` / `/ (root)` → Save
5. After 1–2 minutes the site is live at `https://<username>.github.io/<repo>/`

**Option 3: Netlify Drop**
Drag the whole folder onto [netlify.com/drop](https://app.netlify.com/drop) while signed in to get a public URL.

> **iOS note**: Opening the file directly from WhatsApp/Mail/Files launches the system QuickLook preview, which **disables JavaScript** — the app will appear frozen. This is an iOS security restriction. Use the deployed web link in Safari instead, or transfer the file to a desktop computer and open it there. On Android, Chrome opens the local file fully functional.

### Data Storage & Privacy

| Data | Location | Notes |
|---|---|---|
| Leaderboard scores | Browser `localStorage` | Local-only, isolated per origin; cleared with site data |
| Uploaded dictionaries | Browser `IndexedDB` | Same as above |
| Imported word pools | Browser `IndexedDB` | Same as above |

The app **never** uploads or syncs data to any server. Leaderboards are independent across devices, browsers, and access methods (in-app browser vs Safari vs file://).

### Browser Compatibility

| Environment | Support |
|---|---|
| Desktop Chrome / Edge / Firefox / Safari (recent) | ✅ Full |
| Android Chrome | ✅ Full |
| iOS Safari (web version) | ✅ Full |
| iOS QuickLook preview (direct open in WhatsApp/Files) | ⚠️ Static screen only (JS disabled by the previewer) |

### References / Credits

- **Mr. Chu Bong-Foo (朱邦復)** — Inventor of the Cangjie input method (1976; originally "Sing-Yi character indexing", renamed "Cangjie" in 1978 by Chiang Wei-kuo). Mr. Chu publicly released the method into the public domain in 1982, which is why Cangjie is now built into virtually every Chinese-capable system. This project's dictionary is based on the 3rd-generation codes. See: [Wikipedia · Cangjie input method](https://en.wikipedia.org/wiki/Cangjie_input_method) and [Wikibooks · 倉頡輸入法](https://zh.wikibooks.org/wiki/倉頡輸入法) (composition rules and version history)
- **Sunggang's *Kuai Kuai Le Le* series** — Popular 1990s DOS Chinese-computer tutorial software/books (e.g., *Kuai Kuai Le Le Learns DOS*), the interface inspiration for this project
- **emisjerry** — [cj_jerry.txt Cangjie code table Gist](https://gist.github.com/emisjerry/7a1e72688bfc4d4b5c0f9f16f1b84424), used as the built-in online fallback code table (auto-fetched when deployed over http(s) with no local `chinese.tt`)
- **Cangjie Friends (倉頡之友)** — Reference for 3rd/5th-generation code tables

### License

Released under the [MIT License](LICENSE). The Cangjie method itself carries no copyright restriction (the inventor waived all patents); third-party code tables referenced here remain subject to their original licenses.

---

— ck
`

## 使用提示

- **授權檔**：上方 README 引用了 `LICENSE` 與 MIT——請在儲存庫加一份 MIT 授權文字檔（GitHub 新建儲存庫時可於「Add a license」直接選 MIT 自動生成）；若您想改用其他授權，同步修改 README 的授權段及徽章
- **截圖**：GitHub README 視覺效果以一張 DOS 風格主選單截圖最佳，可後補 `![](docs/screenshot.png)` 於「簡介」段末
- **倉頡 Wikipedia 連結**：中文段落連結含中文字符，GitHub 會自動 URL-encode，直接貼上即可正常跳轉；若您偏好穩妥，可改用英文維基連結統一兩版
- **徽章**：`size` 及 `engine` 徽章為裝飾性，若嫌多可刪；`license` 徽章在補上 LICENSE 檔後即為實際狀態

---

以上都係AI gen出嚟

項目擁有人唔識programming

只係間中去吓HKEPC偷師

如有問題自己fork自己叫AI改即可

90年代.ATC格式檔案請自備

無編碼的字同標點會自動skip
