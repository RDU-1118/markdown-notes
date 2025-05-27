# Linux 作業系統實務 

## 2025/05/06

### 基本指令

#### echo
+ 用來輸出文字或變數內容到終端機的常用指令
+ 語法:`echo [選項] [字串]`

1. 輸出純文字  
   `echo Hello, world!`
   
2. 輸出變數內容  
   `name="Alice"`  
   `echo "Hello, $name"`  

3. 特殊符號  
   
    | 特殊符號 | 說明      |
    | ---- | ------- |
    | `\n` | 換行      |
    | `\t` | 水平跳格    |
    | `\\` | 反斜線 `\` |
    | `\"` | 雙引號 `"` |
    | `\a` | 發出警告聲音  |

#### 寫入檔案
1. `echo "hi" > aaa.txt` 將hi覆寫入aaa.txt檔案裡  

   `cat a.txt` 得到hi  

2. `echo "world" >> aaa.txt`將world加在檔案內容末端
   
   `cat a.txt`得到 hi world  
3. `cat -n filename.txt` 顯示行號
----
#### cat
+ 用來顯示、合併檔案內容的工具

1. `cat a.txt ` 顯示a.txt的內容
2. `cat a.txt b.txt` 顯示多個檔案內容
3. `cat > a.txt` 建立新檔案並輸入內容（Ctrl + D 結束）
4. `cat part1.txt part2.txt > merged.txt` 合併檔案
---
#### prep
+ 用來在檔案或輸出中搜尋特定文字模式的工具
+ 語法: `grep [選項] '字串' 檔案`
  
1. `grep "hello" a.txt` 在a.txt檔案裡 搜尋文字hello
2. `grep -i "hello" a.txt` 忽略大小寫
3. `grep -n "hello" a.txt` 顯示行號
4. `grep -v "hello" file.txt` 反向搜尋
5. `grep "^start" file.txt`    開頭為 start 的資料  
   `grep "end$" file.txt`      結尾為 end 的資料
---
#### ls

+ 用來列出目錄內容
 
   
| 選項             | 說明                       | 範例                |
| -------------- | ------------------------ | ----------------- |
| `-l`           | 以長格式顯示詳細資訊（權限、擁有者等）      | `ls -l`           |
| `-a`           | 顯示所有檔案，包括以 `.` 開頭的隱藏檔案   | `ls -a`           |
| `-h`           | 搭配 `-l` 使用，以人類可讀方式顯示檔案大小 | `ls -lh`          |
| `-t`           | 依照修改時間排序（新→舊）            | `ls -lt`          |
| `-r`           | 反向排序（搭配其他排序選項使用）         | `ls -ltr`         |
| `-S`           | 依照檔案大小排序（大→小）            | `ls -lS`          |
| `-R`           | 遞迴顯示子目錄內容                | `ls -R`           |
| `-d`           | 僅列出目錄本身，而非其內容            | `ls -d */`        |
| `--color=auto` | 自動加上顏色區分檔案類型（多數環境預設開啟）   | `ls --color=auto` |
| `-1`           | 每列顯示一個檔案（常用於腳本中）         | `ls -1`           |

---
#### && 與 || 的用法
1. `mkdir folder1 && cd folder1` 前一個指令成功才執行下一個
2. `cd project || echo "找不到資料夾"` 前一個指令失敗才執行下一個
