## 硬體安全 Hardware Security

針對硬體、物理設備的攻擊，比較常見會攻擊硬體防火牆，而現今會針對硬體安全模組，如加解密、身分驗證等功能的加密金鑰進行討論。

## 硬體安全攻擊類型 Types of Hardware Security Attacks

1. Side-channel attack: 旁通道攻擊，透過收集物理資訊，如電源消耗效率、電磁輻射、時間等資訊，並透過分析該資訊取得有用的內容。
2. Rowhammer attack: 針對電腦記憶體 DRAM 進行攻擊，重複讀取同一段記憶體，造成記憶體的元件受損，進而取得有用的資訊。
3. Timing attack: 定時攻擊，常見於針對破解密碼系統的攻擊手法，如計算系統中處理時間的時間差，計算內容大小不同，時間也會不同，透過重複輸入不同的內容來推測正確輸入。
4. Evil maid attack: 針對無人看守的硬體設備進行攻擊，可能安裝修改軟體的 USB 設備插入電腦中，或是安裝 keylogger 記錄使用者輸入的按鈕。
5. Modification attack: 修改攻擊，常利用中間人攻擊，進而竄改通訊內容。
6. Eavesdropping attack: 竊聽攻擊，竊取通訊過程的封包取得敏感資訊。
7. Triggering fault attack: 觸發故障攻擊，讓硬體設備故障來破壞系統正常執行。
8. Counterfeit hardware attack: 偽裝成其他硬體設備取得敏感資料，供應鏈攻擊。

## 衍生範圍 Scope

1. 物聯網設備安全
2. 工業物聯網安全
3. 晶片安全
4. 車聯網安全

## 防護方法參考 Defense

1. 供應鏈的上下游廠商進行盤點
2. 加密所有設備的介面
3. 最小化可被攻擊範圍
4. 人身安全
5. 即時監控
6. 更新韌體與淘汰舊的硬體
7. 定時稽核

## 參考網址 Reference

- [hardware security](https://www.techtarget.com/searchitoperations/definition/hardware-security)
