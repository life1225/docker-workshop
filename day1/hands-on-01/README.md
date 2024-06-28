- nginx:alpine image 裡的 Nginx
  - 預設網頁會在 `/usr/share/nginx/html` 讀取 index.html
  - 設定檔在 `/etc/nginx/conf.d/default.conf`
- 請在 host 建立一個檔案夾裡面，存放自己編輯的 index.html
- 參考檔案
  - index.html
  - default.conf

## 需求

- 請用 nginx:alpine image 啟動一個 container，以下目標：
  - 利用 bind mounts 的方式將自己的首頁掛載進去
  - 利用 port mapping 的方式，讓 host 的 port # 可以映射到 nginx 的 80
  - 設定 health check，以確定服務運行正常
  - 進階: 建立自己的設定檔，將 Nginx 預設的 port # 80 換成 8080

## 驗證方式

```bash
curl localhost:{mapping 到 host 的 port#}
docker container ls
# 檢查 STATUS 欄位是否為 healthy
```