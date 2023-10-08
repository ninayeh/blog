---
title: 安裝 Joomla3.1.5 - 申請byethost
tags: []
id: '149'
categories:
  - 工具
date: 2013-08-30 05:42:36
---

由於我不是將joomla安裝在本機空間，而是直接裝在免費主機byethost上 因此沒有環境安裝的問題， 這邊只記錄在免費主機上的安裝過程囉(但我想以後還是有機會寫到)
<!-- more -->
# **步驟一 申請**

在查詢安裝joomla的方式中,比較常看見的免費主機有byethost和水世界虛擬主機 而我申請的是byethost 它目前提供的如下: 1000 MB disk space 50 GB monthly transfer FTP account and File Manager Control Panel MySQL databases & PHP Support Free tech support Addon domain(附加網域), Parked Domains(寄放網域), Sub-Domains Free Community Access (Forums) Clustered Servers No ads! ...... 還有很多可以去官網看看  [http://byethost.com/index.php](http://byethost.com/index.php) 到首頁後找到 [Free Host Sign Up](http://byethost.com/free-hosting/news) 的申請頁 填寫資料 (補圖) 比較要注意的是如果固定IP申請的話會出現這樣一段話 **Sorry. We are unable to supply you with an account at this time.** 所以記得要改用浮動IP再來申請 填完資料後,過一陣子,大約5分鐘吧,就會收到驗證信 (補圖) 點擊後輸入驗證碼就會看到 **ACCOUNT ACTIVATED, you will recieve your account details via email very soon.** 就等著收下一封關於VP控制台資料的信囉! 資料大概有這些 Cpanel Username: 主控台帳號 Cpanel Password:  主控台密碼 Your URL:  你網站的位置 FTP Server :  FTP 伺服器位置 FTP Login : FTP使用者名稱 FTP Password : FTP使用者密碼 MySQL Database Name:  MUST CREATE IN CPANEL MySQL Username : 資料庫帳號 MySQL Password :  資料庫密碼 MySQL Server: SEE THE CPANEL Cpanel URL: [http://cpanel.byethost7.com](http://panel.byethost.com/) -> 就是從這裡登入主控台的 不過因為我很快地就把Joomla 安裝進來,而且大部分的資料我是透過FTP或是joomla 內建的方式來上傳 所以VP的控制台我就沒有深入研究了,基本上申請到這邊就結束溜。 ==我應該來裝一下插入分隔線的編輯器)==

## **筆記：**

**Virtual Private Server (VPS) hosting - 虛擬專用伺服器**

> 虛擬專用伺服器（VPS），是指通過虛擬化技術在獨立伺服器中執行的專用伺服器。每個使用VPS技術的虛擬獨立伺服器擁有各自獨立的公網IP位址、作業系統、硬碟空間、記憶體空間、CPU資源等，還可以進行安裝程式、重新開機伺服器等操作，與執行一台獨立伺服器完全相同。--維基百科

**Layered Panel / Vista Panel / cPanel** 這三個都是空間的控制平台(或說儀表板dashboard) 差別是在於空間、流量...等的不同 byethost 免費伺服器使用的是 Vista Panel **疑問待解：** **為什麼明明是 Vista Panel 可是給的訊息是cPanel而且登入版本是cPanel X3?**