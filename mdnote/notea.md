# Linux 作業系統實務 

## 2025/05/20

### 指令
 
####  `adduser` 新增使用者帳號

`adduser` 是 Ubuntu 中用來新增使用者的簡單工具，會自動建立家目錄並引導設定密碼與資訊。

#### 語法：

```bash
sudo adduser [使用者名稱] 
##範例
sudo adduser mary 
```
#### rwx權限t:
+ 用於目錄上，用來限制資料夾中的檔案只能由檔案的擁有者或root 使用者刪除或改名，即使其他人對該資料夾有寫入權限
+ 共用目錄（如 `/tmp`）中的使用者資料不被他人刪除,所以`/tmp`資料夾內的檔案,通常可以用來讓不同使用者做資訊的分享
  
#### lsattr指令

+ 顯示每個檔案的屬性標記，這些標記決定檔案在某些操作下的行為限制
#### 語法：
```bash
lsattr [選項] [檔案或目錄]
##範例
lsattr -d /home/user #顯示目前目錄下所有檔案的屬性
lsattr -R /etc #顯示 /home/user 資料夾本身（而非內容）的屬性
```
常見參數
| 參數  | 說明                                    |
| --- | ------------------------------------- |
| `a` | 只允許**追加**寫入，無法覆蓋或刪除（適用於 log 檔）        |
| `i` | 設為 immutable（不可變），**不能修改、刪除、改名、建立連結** |
| `d` | 在執行 `dump` 備份時會被忽略                    |
| `e` | 檔案使用延伸區塊儲存資料（extents，ext4 通常會有）       |
| `s` | 當檔案被刪除時，內容會被完全清除而不是標記為可覆寫（安全刪除）       |
| `t` | 檔案的最後修改時間不會被更新                        |
| `u` | 檔案刪除後可以被恢復（非所有檔案系統支援）                 |

#### i lock 與 a lock
#### i lock
 - 功能：無法刪除、改名、修改、改權限
 - 適用：保護重要設定檔或防止惡意程式竄改
 ```bash
 ## 範例
sudo chattr +i file.txt    # 啟用
sudo chattr -i file.txt    # 解除
--------------------------
lsattr file.txt
----i-------- file.txt     # 代表該檔案已鎖定
 ```
#### alock
- 只能追加寫入
- 無法清空、覆蓋、刪除檔案內容
```bash
## 範例
sudo chattr +a log.txt     # 啟用 append-only
sudo chattr -a log.txt     # 解除 append-only
--------------------------
lsattr log.txt
-----a------- log.txt
```
#### getfacl
- 顯示檔案或目錄的標準權限與額外的 ACL 權限
```bash 
getfacl [檔案或目錄]
## 範例
getfacl myfile.txt
-------------------------
# file: myfile.txt
# owner: user1
# group: user1
user::rw-
user:alice:r--
group::r--
mask::r--
other::r--
```
