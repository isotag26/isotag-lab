# IsoTag Lab 網站

純靜態網站(HTML + CSS),可直接放上 GitHub Pages。

## 檔案結構

```
index.html          首頁
research.html       研究主題
team.html           成員
publications.html   論文
news.html           最新消息
join.html           招生
contact.html        聯絡
assets/style.css    全站樣式(最上面的 :root 可改主色、字型)
assets/main.js      手機選單
images/             圖片
.nojekyll           讓 GitHub Pages 直接發布,不經 Jekyll 處理
```

## 常見修改

- **換首頁大圖**:用實驗室照片覆蓋 `images/hero.jpg`(建議橫式、寬 1600px 以上)。
- **放成員照片**:把照片放進 `images/`,再把 `<div class="ph square">Photo</div>` 換成
  `<img src="images/檔名.jpg" alt="姓名">`。
- **新增論文 / 消息**:頁面裡有註解說明,複製一個 `<li>` 改內容即可。
- **導覽列**:每一頁最上面的 `<nav>` 都要一起改。

## 在區網內給老師預覽

在自己電腦上打開這個資料夾,開終端機執行:

```
python3 -m http.server 8000 --bind 0.0.0.0
```

(Windows 用 `python -m http.server 8000 --bind 0.0.0.0`)

再查自己電腦的區網 IP(Windows:`ipconfig`;macOS:系統設定 → 網路),
老師在同一個 Wi-Fi 下用瀏覽器開 `http://你的IP:8000` 即可。
若打不開,通常是防火牆擋住,允許 Python 的連線就好。
注意:學校 Wi-Fi 有時會隔離裝置之間的連線,這種情況請改用下面的 GitHub Pages。

## 發布到 GitHub Pages

1. 在 GitHub 建一個新的 repository(例如 `isotag-lab`),設為 Public。
2. 把這個資料夾的所有檔案上傳(網頁上 "Add file → Upload files" 拖進去即可)。
3. 到 repository 的 **Settings → Pages**,Source 選 **Deploy from a branch**,
   Branch 選 `main`、資料夾選 `/ (root)`,按 Save。
4. 約一分鐘後網址會出現:`https://你的帳號.github.io/isotag-lab/`

想要 `帳號.github.io` 這種短網址,把 repository 名稱取為 `你的帳號.github.io`。
之後要綁學校或自訂網域,同一頁的 **Custom domain** 填入即可。
