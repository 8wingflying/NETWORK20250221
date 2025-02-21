# NETWORK20250221
- 網路基礎架構與網路服務研習班
- 114年2月21日(星期五)
# [教材下載](網路基礎架構與網路服務研習班_20250221.pdf)
# 課程內容
- 網路概論
- Wireshark 分析{參考實作練習} [補充簡報](wireshark網路封包分析.pdf)
  - 完成 實作練習1:WIRESHARK安裝
  - 完成 實作練習2:封包側錄
- 網路服務與協定分析 {搭配實作練習3說明}
  - 應用層協定: DNS
    - ...有很多 有時間依序介紹
    - (1)EMAIL 用的 SMTP|POP3|IMAP4
    - (2)HTTP .....
  - 傳輸層協定: TCP UDP
    - ..有時間依序介紹
    - SCTP串流控制傳輸協定(Stream Control Transmission Protocol)
    - QUIC
    - T/TCP == > (略) [安全有疑慮 see Security Problems Associated With T/TCP](https://web.archive.org/web/20010305122504/http://www.mid-way.org/doc/ttcp-sec.txt)
  - 網路層協定: IP  [ICMP](ICMP.pdf)
- [線上實作測驗](https://github.com/8wingflying/NETWORK20250221/tree/main/labS/%E7%B7%9A%E4%B8%8A%E5%AF%A6%E4%BD%9C%E8%80%83%E9%A1%8C)
- 網路管理(Network Management)與SNMP協定 [補充簡報](SNMP.pptx)
  - SNMP的常用工具:
    - Net-SNMP
    - iReasoning MIB browser（提供免费版本）
    - PRTG（提供100个Sensor的免费版本）| MRTG
    - Zabbix（開源免费）
    - Cacti（開源免费） 
- 網路規劃與設計
  - [網路架構規劃參考指引(修訂)v3.1_1101231](網路架構規劃參考指引(修訂)v3.1_1101231.pdf) 
- 網路鑑識(Network Forensics)
  - 網路鑑識(Network Forensics)意義
  - MITRE D3FEND網路流量分析
  - 網路鑑識常用工具
  - 網路鑑識主題
  - 網路鑑識實務技術
    - Wireshark常用技術
    - tshark分析技術
    - NetworkMiner網路鑑識
      - [PCAP封包](https://github.com/8wingflying/NETWORK20250221/tree/main/練習封包/http_witp_jpegs.cap) 


# 實作練習
### 實作練習1:WIRESHARK安裝
### 實作練習2:封包側錄
### 實作練習3:封包分析 [參考解答](協定分析實戰.pdf)
- [待分析之封包](https://github.com/8wingflying/NETWORK20250221/blob/main/labS/Cennection2Google.pcapng)
- 1.DNS 封包分析
  - lab1.第262個封包所查詢的域名是什麼?
  - lab2.DNS server的IP?
  - lab3.GOOGLE的ip是多少?  
- 2.TCP封包分析
  - lab1.第20個封包的port是什麼?
  - lab2.找出 20號封包三向交握有關的另外兩個封包並說明Three-way Handshaking
- 3.UDP封包格式分析
  - lab1.第16個封包的Destination Port是多少?  
- 4.IP封包格式分析
  - lab1.第87個封包的IP裡面有一個 Time to live 後面的數字是多少?

### 實作練習4:網路鑑識分析實戰
```
機關SOC 分析師正在檢查 SIEM 警報，並察覺到有關連線到已知惡意網址的警報。
流量是來自 Sara 的電腦，她是一名會計師，每天都會收到大量客戶發送的電子郵件。
查看 Sara 信箱的電子郵件日誌，並沒發現任何可疑之處，電子郵件來自客戶。
透過電話聯繫Sara ，她說一位客戶向她發送了一張發票，其中包含帶有巨集的文件，
她打開電子郵件，程式就崩潰了。
SOC 團隊取回了 PCAP 進行進一步分析。
```
- [待分析的PCAP](https://github.com/8wingflying/NETWORK20250221/tree/main/練習封包/traffic-with-dridex-infection.pcap)
- TASK任務
  -	問題1:感染主機的私有IP是多少？
  -	問題2:巨集文件嘗試檢索的惡意軟體二進位是什麼？
  -	問題3:帶有 GET /images/ 的 HTTP 請求來自哪個網域？
  -	問題4:SOC 團隊發現 Dridex(Ursnif 感染的後續惡意軟體)是罪魁禍首。向她發送巨集文件的客戶已被洩露。Ursnif 從中檢索後續惡意軟體的以 .rar 結尾的完整 URL 是什麼？(格式：http://(網域或IP)/file.rar)
  -	問題5:以 185 開頭的 Dridex 感染後流量 IP 位址是？
- 參考資料 https://www.malware-traffic-analysis.net/2018/11/27/index.html
  - Dridex 惡意流量分析
  - Dridex 是惡名昭彰的銀行木馬，它能夠竊取使用者憑證並對主機的檔案系統進行修改。還可以將自身注入瀏覽器與網站，非法獲取使用者登入資訊
  - Dridex傳遞方式通常透過包含惡意文件與/或惡意連結的網路釣魚電子郵件進行
  - 本實作將檢視與分析Dridex 惡意流量 
- 分析技巧
  - 實作內容A:使用Wireshark分析
  - 實作內容B:使用NetworkMiner分析
  - 實作內容C:使用PCAP線上平台分析

# 延伸閱讀
- 計算機網路
  - 經典 Computer Networks 電腦網路 | Andrew S. Tanenbaum
    - [英文版(最新版第六版)](https://www.tenlong.com.tw/products/9781292374062?list_name=srh)
    - [簡體中譯本(最新版第六版)](https://www.tenlong.com.tw/products/9787302604716?list_name=srh)
    - [中譯本(第五版)](https://www.tenlong.com.tw/products/9789862800973?list_name=srh)  
  - William Stallings
    - [現代網絡技術：SDN、NFV、QoE、物聯網和雲計算](https://www.tenlong.com.tw/products/9787111586647?list_name=srh)
      - Foundations of Modern Networking: SDN, NFV, QoE, IoT, and Cloud
- 資料與電腦通訊
  - [資料與電腦通訊, 8/e (Data and Computer Communications, 8/e) |William Stallings](https://www.tenlong.com.tw/products/9789861815510?list_name=srh) 
  - [通訊原理, 7/e (Principles of Communications, 7/e)| Rodger E. Ziemer , William H. Tranter](https://www.tenlong.com.tw/products/9789869190329?list_name=srh)
- Wireshark
  - [網路分析完全實戰手冊 ─ 使用 Wireshark, 2/e| Nagendra Kumar Nainar、Yogesh Ramdoss、Yoram Orzach](https://www.tenlong.com.tw/products/9789864343973?list_name=srh)
    - Network Analysis using Wireshark 2 Cookbook, 2/e
- 網路鑑識| Network Forensics
  - [Packet analysis for network forensics: A comprehensive survey](https://www.sciencedirect.com/science/article/pii/S1742287619302002)
  - [Hands-On Network Forensics](https://learning.oreilly.com/library/view/hands-on-network-forensics/9781789344523/)
