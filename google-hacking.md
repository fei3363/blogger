新手入門必學的技巧，學會 Google 你也可以輕鬆上手資訊安全，不管你是要進行資安檢測還是查詢資料，Google 都是非常好用的工具，本篇文章介紹如何透過 Google 找尋你要的資料，透過簡單的語法，找到指定的資訊，是滲透測試中被動搜查最好用的工具。

### Why

為什麼要利用搜尋引擎找到有關於目標的資訊。
因為搜尋引擎最方便，透過瀏覽器最容易可以使用。

### Google 搜尋

你會用 google 當然駭客也會用 google!

![//](https://feifei.tw/wp-content/uploads/2022/04/post-78-62531afa099e1.png)### Google Hacking 語法表

一般人使用:如何當駭客
駭客使用：site:feifei.tw

| 語法 | 說明 | 範例 |
|--------|--------|--------|
| `+` | 連接多個關鍵字 | -- |
| `-` | 忽略關鍵字 | -- |
| `..` | 範圍 | -- |
| `*` | 萬用字元 | -- |
| `` | 精準查詢，一定要符合關鍵字 | `index of` |
| `intext` | 搜尋網頁內容，列出符合關鍵字的網頁 | `intext:SECRET_KEY=` |
| `intitle` | 搜尋網頁中的標題 | `intitle:index of` |
| `cache` | 搜尋指定網址的快取、緩存 | `cache:網址` |
| `define` | 搜尋關鍵字的定義 | `define:hacker` |
| `filetype` | 搜尋指定類型的文件 | `filetype:pdf` |
| `info` | 搜尋指定網站的基本資訊 | `info:www.fcu.edu.tw` |
| `related` | 搜尋類似於指定網站的其他網站 | `related:www.fcu.edu.tw` |
| `inurl` | 尋找指定的字串是否在網址列當中 | `inurl:www.fcu.edu.tw` |
| `site` | 搜尋指定網址的內容 | `site:www.fcu.edu.tw` |

### Google 進階搜尋

Q:針對 google 的進階用法，一定要背這些語法嗎？
A:一開始可以使用 Google 頁面的「進階搜尋」，用久了就會記得。

1. 進入 [`https://www.google.com/`](https://www.google.com/)，點選右下角的進階搜尋。
  ![](https://feifei.tw/wp-content/uploads/2022/04/post-78-62531afb919a2.)
2. 進入 [`https://www.google.com/advanced_search`](https://www.google.com/advanced_search)
  ![](https://feifei.tw/wp-content/uploads/2022/04/post-78-62531afd4153a.)
3. 選擇指定的類別
  ![](https://feifei.tw/wp-content/uploads/2022/04/post-78-62531afee05f3.)

### 真實案例與搜尋目標

Q:有什麼真實案例可以分享的？
A:許多工程師貪圖方便或是沒有注意，會把帳號密碼一起上傳到正式的環境中，若被 google 收錄，將造成嚴重的敏感資料外洩。

Q:可是我不知道要蒐集什麼，什麼資料是我的目標？
A:

1. 網路設定檔案
2. 包含企業內部的信箱
3. 企業使用的帳號格式
4. 帳號、密碼、私鑰
5. 第三方服務、雲端服務的設定檔案
6. 錯誤訊息
7. 正在開發、測試中、使用者測試、歷史版本的網站

### Robots.txt

Q:搜尋目標除了從域名下手，也可從那些路徑下手呢？
根目錄底下的 `robots.txt` 該檔案為了要提供給搜尋引擎使用，搜尋引擎其實是一個巨大的「爬蟲」，每天都會爬大量的網站收錄在自己的資料庫中，有哪些路徑要提供給搜尋引擎爬，有那些不想讓搜尋引擎收錄，都可以在 `robots.txt` 被定義。

```
<pre class="wp-block-code">```
<pre class=wp-block-code>```
User-agent: Googlebot
Disallow: /nogooglebot/

User-agent: *
Allow: /

Sitemap: http://www.example.com/sitemap.xml

```
```

- `User-agent`：指定的 bot 他請求時所代的 User-agent，`*` 為萬用字元，符合所有機器人。
- `Disallow`：不允許收錄的路徑
- `Allow`：允許收錄的路徑
- `Sitemap`：路徑地圖

這些不被允許收錄的路徑，可能就包含敏感路徑，如登入口，滲透測試可以從這個點下手。

#### Google Hacking, or Dorking

進入網站[ Google Hacking Database](https://www.exploit-db.com/google-hacking-database) 後，選取右邊的 Filters 可查詢指定的類型。

![/](https://feifei.tw/wp-content/uploads/2022/04/post-78-62531b010a5a0.png)| GHDB 類型 | 說明 |
|-------------|--------|
| Footholds | 找尋突破口(立足點) |
| Files Containing Usernames | 包含使用者帳號的檔案 |
| Sensitive Directories | 敏感資料夾 |
| Web Server Detection | 網站伺服器偵測 |
| Vulnerable Files | 有弱點的檔案 |
| Vulnerable Servers | 有弱點的伺服器 |
| Error Messages | 錯誤訊息 |
| Files Containing Juicy Info | 敏感檔案內包含有用的資料 |
| Files Containing Passwords | 敏感檔案內包含密碼 |
| Sensitive Online Shopping Info | 敏感的網路購物資訊如卡號 |
| Network or Vulnerability Data | 網路中可能含有弱點的頁面如 log |
| Pages Containing Login Portals | 包含登入資訊的頁面 |
| Various Online Devices | 正在網路的設備如印表機或攝影機 |
| Advisories and Vulnerabilities | 有漏洞和警告訊息的頁面 |

### google map

許多人在 Google Map 的地圖中，可以推薦與評論，但是上傳照片時，沒有注意照片裡面是否包含敏感資訊，如咖啡廳的 wifi 密碼，或是會議室的紙條，因此 google map 也可以是蒐集資訊的好工具。

### 飛飛的鐵人賽連結

- [Day 6 被動搜查(3)-Google Hacking、shadon、.git 洩漏](https://ithelp.ithome.com.tw/articles/10269308)
- [資安補帖─Day2─想學資安，先學寫程式&利用Google當個駭客(談Google Hacking)](https://ithelp.ithome.com.tw/articles/10201068)
