# Redis-Sentinel-Docker-Compose

An example setup for using Redis Sentinel with Docker Compose.

See my blog post for more information and an explanation: https://blog.alexseifert.com/2016/11/14/using-redis-sentinel-with-docker-compose/

GOOS=linux GOARCH="amd64" go build main.go
GOOS=darwin GOARCH="amd64" go build main.go
GOOS=windows GOARCH="amd64" go build main.go

Total=100000 Thread=10 RedisMasterName=redismaster RedisAddress=192.168.1.8:26369,192.168.1.9:26369,192.168.1.10:26369 ./test_redis

Total=1000 Thread=10 Url="https://vndapi-dlink.stockbook.vn/app/registered_users/4785074604893743?limit=500&offset=0" ./test_api_linux
Total=100 Thread=10 Url="http://loginsvr.netalo.svc.cluster.local:8080/app/registered_users/4785074604893743?limit=500&offset=0" ./test_api_linux

Total=10 Thread=10 Url="https://vndapi-dlink.stockbook.vn/app/registered_users/4785074604893743?limit=500&offset=0" go run test_api.go

docker build -t haproxy-server .
redis-cli monitor | grep -E ' "(g|s)et" '
docker-compose -f app.yml up --build