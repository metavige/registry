
## 目的

測試目前版本的 docker registry 設定方式  
主要要做到幾點  

- registry mirror
- image layer persistent

## 測試結果

自己設定會有問題，所以先啟動一個 registry，然後複製裡面的 config.yml 來修改  

### registry mirror

自己透過[官方文件](https://docs.docker.com/registry/recipes/mirror/)裡面的設定方式，目前沒測試出來  
但是複製 registry 原先預設的 config.yml 修改一下就可以了  

### persistent
  
如果要改變存放位置，只需要變更 docker-compose.yml 中 `${PWD}` 的位置就可以  

我之前的設定並沒有設定下面的部分，檢查了 [registry config](https://docs.docker.com/registry/configuration/) 文件部分，需要注意的就是  
裡面標記是 required 的部分就是一定要輸入的  
我想我就是少了下面的部分才會有問題  

```yaml
http:
  addr: :5000
  headers:
    X-Content-Type-Options: [nosniff]
health:
  storagedriver:
    enabled: true
    interval: 10s
    threshold: 3
```