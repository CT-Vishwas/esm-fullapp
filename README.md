# esm-fullapp
- Backend is based on GO
We use below as backend services on docker or podman
- MongoDB
- Mysql
- Redis
- Localstack
- Flagsmith

Inside folders create .envs or set environment variables
- `service-event`
```text
LOCALSTACK_AUTH_TOKEN=<your localstack auth token>
MONGO_URI=mongodb://mongouser:mongouser@localhost:27017/?authSource=admin
PORT=8081
```
- `service-booking`
```text
DATABASE_URL=root:root@tcp(localhost:3306)/booking_db?charset=utf8mb4&parseTime=True&loc=Local
FLAGSMITH_ENVIRONMENT_KEY=<Add Flagsmith key>  # ◄ ADD YOUR SERVER SIDE SDK KEY HERE
AWS_S3_BUCKET=ems-tickets-bucket
AWS_REGION=us-east-1
AWS_S3_ENDPOINT=http://localstack:4566
AWS_ACCESS_KEY_ID=test
AWS_SECRET_ACCESS_KEY=test
REDIS_ADDR=localhost:6379
REDIS_PASSWORD=redisuser
```
- `gateway-graphql`
```text
EVENT_SERVICE_URL=http://localhost:8081
BOOKING_SERVICE_URL=http://localhost:8082
```

- Run `go get .` in every service 
- 