# 🌐 個人網站專案 (Hexo + GitHub Pages)

## 📖 專案背景 (Overview)
這是一個基於 **Hexo + GitHub Pages** 的個人部落格專案。
定位結合 **生活分享、專業學習筆記、國際交流紀錄**，目標是：
- ✨ 建立個人品牌，累積 SEO 長期流量
- 📊 展示數據分析與專案成果
- 🌍 分享海外實習、語言學校與國際交流經驗

### ⚡ 注意
本專案 (**myblog**) 為網站的 **原始碼開發倉庫**，包含 Hexo 設定檔、主題與 Markdown 文章。  

每次執行 `hexo deploy` 時，系統會將編譯後的靜態檔案輸出到另一個部署倉庫：  
👉 https://github.com/melodykao000/melodykao000.github.io  

**網站實際瀏覽網址**：  
👉 https://melodykao000.github.io


---

## 🗂 目錄 (Table of Contents)
- [專案背景](#-專案背景-overview)
- [技術架構](#-技術架構)
- [環境需求](#-環境需求)
- [安裝流程](#-安裝流程-installation)
- [使用指令](#-使用指令)
- [專案架構](#-專案架構)
- [文章撰寫與 SEO 規範](#-文章撰寫與-seo-規範)
- [自訂網域 (選用)](#-自訂網域-選用)
- [常見問題 FAQ](#-常見問題-faq)
- [後續規劃](#-後續規劃)
- [作者](#-作者)
- [授權](#-授權)

---

## 🛠 技術架構
- **Hexo**：靜態網站生成器
- **Icarus 主題**：可自訂 UI/UX
- **GitHub Pages**：免費託管，支援 HTTPS
- **Node.js + npm**：開發與套件管理
- **自訂網域**（規劃中）：建立專屬品牌網址

---

## 🧰 環境需求
- Node.js ≥ 18（建議 LTS）
- npm ≥ 9
- Git

---

## ⚡ 安裝流程 (Installation)

1. **Clone 專案**
   ```bash
   git clone https://github.com/your-username/your-repo.git
   cd your-repo
   ```

2. **安裝套件**
   ```bash
   npm install
   ```

3. **(選用) 設定站點基本資訊**
   在 `\_config.yml` 內設定：
   ```yaml
   title: 我的個人網站
   subtitle: "用數據和故事，記錄世界"
   description: "生活、旅遊、數據分析與國際交流的筆記"
   url: https://your-domain.com   # 尚未購買網域可先留空或用 GitHub Pages 網址
   ```

4. **啟動本機伺服器**
   ```bash
   npm run start
   ```
   預設網址：http://localhost:4000

5. **部署到 GitHub Pages**
   ```bash
   npm run deploy
   ```

---

## 🚀 使用指令

### 快捷鍵（package.json）
```json

{

&nbsp; "scripts": {

&nbsp;   "start": "hexo clean \&\& hexo g \&\& hexo s",

&nbsp;   "deploy": "hexo clean \&\& hexo g \&\& hexo d"

&nbsp; }

}

```

### 原生 Hexo 指令
```bash

hexo clean      # 清除快取與舊檔案

hexo generate   # 產生靜態檔案 (簡寫：hexo g)

hexo server     # 啟動本機伺服器 (簡寫：hexo s)

hexo deploy     # 部署到 GitHub Pages (簡寫：hexo d)



hexo new "文章標題"   # 建立新文章

```

---

## 📂 專案架構
```text

my-blog/

├─ node\_modules/

├─ public/               # 產生後的靜態檔案

├─ scaffolds/

├─ source/

│  ├─ \_posts/            # 文章 Markdown

│  └─ CNAME              # (選用) 自訂網域檔案

├─ themes/

│  └─ icarus/            # 主題檔案

├─ \_config.yml           # Hexo 全域設定

├─ package.json          # npm 設定（含快捷鍵）

└─ README.md             # 本文件

```

---

## 📝 文章撰寫與 SEO 規範

### 撰寫方式
在 `source/\_posts/` 新增 Markdown 檔案，檔頭需包含 Front‑matter，例如：
```yaml

title: 我的第一篇文章

date: 2025-08-20 12:00:00

categories: \[Life]

tags: \[旅遊, 美食]

description: "這是一篇旅遊心得，記錄在貝里斯實習期間的生活點滴。"

\# (選用)

\# thumbnail: /images/cover/belize.jpg

\# og\_image: /images/cover/belize-og.jpg

```

### SEO 清單（每篇文章）
- 明確的 `title`（含主要關鍵字，≤ 60 字元）
- `description` 120–160 字摘要（含主關鍵字）
- 內文使用清楚的 **H1/H2/H3** 層級結構
- 圖片檔名語意化、加上 `alt` 文字
- 適度插入 **內部連結**（舊文互鏈）
- 每篇聚焦 1 個主題（避免關鍵字稀釋）

### Sitemap 與 robots（選用但推薦）
安裝外掛：
```bash

npm i -S hexo-generator-sitemap hexo-generator-robots

```
於 `\_config.yml` 加上：
```yaml

sitemap:

&nbsp; path: sitemap.xml



robots:

&nbsp; useragent: "\*"

&nbsp; allow:

&nbsp;   - /

&nbsp; sitemap: https://your-domain.com/sitemap.xml

```

---

## 🌐 自訂網域 (選用)
1. 購買網域並在 DNS 設定 CNAME → `your-username.github.io`
2. 在 GitHub 專案 **Settings → Pages → Custom domain** 填入你的網域
3. 在 `source/` 目錄新增 `CNAME` 檔，內容只放你的網域：
   ```
   your-domain.com
   ```
4. 重新部署後，啟用 HTTPS（GitHub Pages 會自動簽 SSL）

---

## ❓ 常見問題 FAQ

**Q1：部署後手機分享預覽出現主題預設縮圖？**
A：為文章加上 `og\_image`（或 `thumbnail/cover`）並確保該路徑能被公開存取；重新部署後，用社群平台的 Debug 工具重新抓取快取。

**Q2：`hexo s` 有改檔案但頁面沒變？**
A：先 `hexo clean \&\& hexo g \&\& hexo s`；或確認瀏覽器快取是否清除。

**Q3：Git 顯示 `LF will be replaced by CRLF` 警告？（Windows）**
A：可設定：
```bash

git config core.autocrlf false

```
或在 `.gitattributes` 指定：
```

\*.md text eol=lf

\*.yml text eol=lf

\*.css text eol=lf

\*.js  text eol=lf

```

**Q4：部署失敗或 404？**
A：確認 `\_config.yml` 的 `deploy` 設定與 GitHub repo 名稱正確、Token 權限可推送；必要時重新產生 Token。

---

## 🔮 後續規劃
- 新增 **Portfolio** 頁面 → 展示專案與作品
- 綁定 **自訂網域** → 專業品牌網址
- 優化 **UI/UX**
- 訂閱功能 (Newsletter) → 建立讀者社群

---

## 👩‍💻 作者
- **melody kao**
- Email：melodykao000@gmail.com

---

## 📜 授權
© 2025 melody kao.  
程式碼採用 MIT 授權 | 文章與圖片內容採用 CC BY-NC 4.0 授權
