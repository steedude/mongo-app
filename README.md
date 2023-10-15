### 本地端測試

docker-compose -f docker-compose-dev.yml up

### 伺服器上部署

docker-compose -f docker-compose-prod.yml up

docker-compose -f docker-compose-nginx.yml up -d
docker-compose -p mongo-app-dev --env-file dev.env -f docker-compose.yml up -d
docker-compose -p mongo-app-prod --env-file prod.env -f docker-compose.yml up -d

docker-compose --env-file dev.env -f docker-compose.yml up -d

docker-compose -f olds/docker-compose-dev.yml up -d
docker-compose -f olds/docker-compose-prod.yml up -d
