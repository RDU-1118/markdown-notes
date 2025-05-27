# Linux 作業系統實務 

## 2025/04/22 ~ 05/06

### docker
+ 安裝:先執行  
`sudo apt update`  
後再執行  
`sudo apt install ca-certificates curl gnupg lsb-release` 

+ 執行`sudo docker info` 可查看docker的相關資訊
+ 執行`sudo docker run hello-world`檢查是否安裝成功

#### 新增docker金鑰
1. `sudo mkdir -p /etc/apt/keyrings`
2. `curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gp`
+ 登入[docker hub](https://docs.docker.com/engine/install/ubuntu/ "Title") 後取得金鑰
#### 基本指令
+ `docker ps` 查看目前正在執行的容器`-a`包含已停止運作的容器

+ `docker images` 查看映像檔列表

+ `docker pull <image-name>` 從 Docker Hub 下載映像檔  

+ ` docker start <container-id>` 啟動容器  
  `docker stop <container-id>` 停止容器  
  `docker restart <container-id>` 重啟容器  

+ `docker rm <container-id>` 刪除容器  
  `docker rmi <image-id>` 刪除映像檔 

+ `docker run --name mydockerer -it ubuntu `建立並執行mydocker (有名字的) 容器
   
+ `docker run -v /host/path:/container/path -it ubuntu` 連結容器與主機

+ `docker run -d <image-name>` 後台執行容器
#### 利用瀏覽器瀏覽執行的容器
1.  執行`docker run -d --name {dockernam} -p 8080:80 httpd` 掛載容器
2.  在瀏覽器輸入docker回應的網址即可查看
+ ![alt text](markdown-notes/20250422_docker/image-1.png)
