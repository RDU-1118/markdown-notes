# Linux 作業系統實務 

## 2025/02/25

### ubuntu的應用
#### 匯出虛擬機

+   在VMware中找到 ```file``` 選單中選擇```export to OVF...``` 並選擇匯出路徑即可
---
#### ssh相關指令
 
+ **找到本機ip地址**

     開啟Terminal輸入 ```ip address show ```或使用縮寫```tp a s ```即可   
    ![查看本機 IP 的截圖](20250218/螢幕擷取畫面%202025-02-18%20110336.png)
---
#### 控制及查詢TCP/IP網路介面指令
  + 在Terminal中輸入 ```ifconhig``` 來查詢,若無法執行須先安裝相關軟體
  
   ![alt text](<20250218/螢幕擷取畫面 2025-02-18 113839.png>)
  
  + 輸入 ```sudo apt install net-tools``` 並輸入管理員密碼取得root權限來安裝
   
   ![alt text](<20250225/螢幕擷取畫面 2025-02-25 104147.png>)
---
#### Network connation

+ NAT  
  使用此方式可以讓 **host** 端與 **guest** 端互相取得連線
+ bridge  
  是點對點對接的方法
--- 

#### ping指令

+ ping可以用來確認裝置監是否互相連線
+ 在Terminal中輸入```ping ip位址``` 有回應代表兩部裝置可互相通訊
  ![alt text](<markdown-notes/20250225/螢幕擷取畫面 2025-02-25 103432.png>)
---

#### ssh遠端通訊
+ 在Terminal中先取得root權限後輸入``` apt install openssh-sever``` 想要一鍵安裝可以在後面加一個 ```-y```安裝過程中會將全部選項預設yes
 ![alt text](<markdown-notes/20250225/螢幕擷取畫面 2025-02-25 111229.png>)
+ 在Terminal中輸入```systemctl status ssh``` 可以查看伺服器是否啟動
  ![alt text](<markdown-notes/20250225/螢幕擷取畫面 2025-02-25 111304.png>)
+ 若未啟動可以輸入``` systemctl start ssh```來啟動,```systemctl stop ssh```來關閉  
    
+ 在Terminal中先取得root權限後輸入``` netstat -tunlp``` 可以查看練接獲開啟的伺服器
 ![alt text](<markdown-notes/20250225/螢幕擷取畫面 2025-02-25 111426.png>)
---
#### 與ssh連線
*在ubuntu中*
+ 在Terminal中輸入```ssh -p 22 user@ssh ip位址```並輸入帳號密碼後即可取得連線
  ![alt text](<markdown-notes/20250225/螢幕擷取畫面 2025-02-25 113748.png>)
  
*在Windows中* 
+ 安裝 [putty](https://www.putty.org/) 或其他連接軟體後輸入ip位址及帳號密碼即可
 ![alt text](<markdown-notes/20250225/螢幕擷取畫面 2025-02-25 112856.png>)
+ 安裝 [WinSCP](https://winscp.net/eng/download.php) 登入後即可取得ssh伺服器中的檔案
  ![alt text](<markdown-notes/20250225/螢幕擷取畫面 2025-02-25 120549.png>)




 
  

[def]: </ubuntu_vt/筆記/20250225/螢幕擷取畫面 2025-02-25 100310.png>