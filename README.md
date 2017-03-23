
## 目的

測試目前版本的 docker registry 設定方式
主要要做到幾點

- registry mirror
- image layer persistent

## 測試結果

### registry mirror

透過[官方文件](https://docs.docker.com/registry/recipes/mirror/)裡面的設定方式，目前沒測試出來
但是我採用 environment 方式，設定 `REGISTRY_PROXY_REMOTEURL` 就可以

### persistent

同上，我採用 config.yml 設定目前不能運作
