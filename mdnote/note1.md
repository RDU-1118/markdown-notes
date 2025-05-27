# Linux 作業系統實務    

## 2025/02/18

+ 安裝虛擬機
  
    下載虛擬機軟體 [vmware](https://www.vmware.com/products/desktop-hypervisor/workstation-and-fusion)
+ 下載 [ubuntu](https://ubuntu.com/download/desktop)
+ 掛載ubuntu的iso檔
  ![alt text](../markdown-notes/20250218/image.png)
  ![alt text](../markdown-notes/20250218/image-1.png)
+ 設定使用者名稱及密碼並依照現有硬體設備給予適合的硬體資源
  ![alt text](../markdown-notes/20250218/image-2.png)
+ 安裝完成
  ![alt text](../markdown-notes/20250218/螢幕擷取畫面%202025-02-18%20110336.png)
---
### 取得root權限
+ 開啟Terminal(終端機)輸入 ``` sudo passwd root ```提升權限到管理者,並且修改管理者密碼
+ 修改好後在Terminal中輸入```su``` 指令可以讓一般的Linux 使用者取得 root 權限
---
### 虛擬機快照
+ 對想要快照的虛擬機按右鍵,在選單中找到 Snapshot 附錄中選擇Take Snapshot... 
  ![alt text](../markdown-notes/20250218/螢幕擷取畫面%202025-02-18%20113839.png)
---
### 克隆虛擬機
+ 對想要克隆的虛擬機按右鍵,在選單中找到 Manage 附錄中選擇
  clone...
  ![alt text](../markdown-notes/20250218/image-3.png)
+ 修改虛擬機名稱
  在Terminal中輸入```su``` 取得root權限後接著輸入
  ``` hostnamectl set-hostname 作業系統名稱``` 後重新啟動
  即可
---