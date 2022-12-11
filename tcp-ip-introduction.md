## TCP/IP 協定

**制定溝通方式的規則**

網路利用 TCP/IP 各種協定在運作，網路設備如果要互相溝通，必須要使用相同的「溝通方式」，

1. 如何找到溝通的目標
2. 誰先開始進行溝通
3. 用什麼語言溝通
4. 怎麼樣才算是結束溝通 …等等

**需要定義以上種種規則，這些規則就叫做「協定」(protocol)**

## TCP/IP 分層管理

**分層好處多多**

1. 分層讓管理更方便
2. 分層讓設計更簡單
3. 簡單分成四層
(1) 應用層
(2) 傳輸層
(3) 網路層
(4) 連結層

## TCP/IP 傳輸方向

**了解每一層傳輸過程中做了什麼事情**

- 請求封包： 使用者端(應用層 -> 傳輸層 -> 網路層 -> 連結層 ) -> 伺服器端(連結層 -> 網路層 -> 傳輸層 -> 應用層)
- 回傳封包： 伺服器端(應用層 -> 傳輸層 -> 網路層 -> 連結層 ) -> 使用者端(連結層 -> 網路層 -> 傳輸層 -> 應用層)

經過每一層會加上該層的 header：把封包包裝起來->封裝 encapsulate

## 網頁傳輸過程中會遇到的協定

1. 網路層 — Internet Protocol
2. 傳輸層 — Transmission Control Protocol
3. 應用層 — Domain Network System (DNS) protocol

**網路層 — Internet Protocol**

將各種「封包」確實傳送給目的地，需要具備 IP address 和 MAC address。

1. IP address：該設備被分派到的網路地址。
2. MAC address：網路卡固定的地址，基本上不會改變。

在 IP 中互相溝通，必須仰賴 MAC Address，透過 ARP 協定（Address Resolution Protocol）解析地址，可協定將 IP address 反查對應的 MAC addreess。

傳輸過程中，會經過很多電腦、網路設備如 Router、AP、小烏龜、基地台等，找到一台可到目的地的路徑稱為 路由（Routing）。

**傳輸層 — Transmission Control Protocol**

為了確保傳輸過程中「確實」將封包傳給目的地，在傳輸層中使用 TCP 協定，會將封包切成較小的格式（segment），進行傳輸。

並透過「三方交握」的方式：

(1) 發送 SYN（synchronize） 給對方

(2) 對方回傳 SYN/ACK

(3) 再發 ACK（acknowledgement） 給對方

之後就會進入連線模式，如果斷線會進行相同的步驟，發送原本的封包，以確保封包的可靠性。

**應用層 — Domain Network System (DNS) protocol**

DNS 用來解析域名與 IP 的系統。

因為人腦並不擅長記 IP。
