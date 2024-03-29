# docker部署測試

## 主要功能

可以在一個伺服器上同時部署兩個環境，彼此獨立運行，共用網路。

## 本地端測試

```bash
docker-compose -f docker-compose-dev.yml up
```

```bash
npm run dev
```

## 伺服器上部署

伺服器放在aws，透過github自動部署，分別部署在
[prod.silver-tercel](https://prod.silver-tercel.com/)
[dev.silver-tercel](https://dev.silver-tercel.com/)

## 部署的邏輯

nginx透過`/var/run/docker.sock:/var/run/docker.sock:ro`可以去跟其他容器溝通，直接讀取其他容器中environment，取得port和host等資訊完成部署。

## 注意事項

因為aws是用免費的方案，儲存空間不夠，可能會導致nginx-proxy-acme無法更新SSL憑證，需要定期清理一下儲存空間
