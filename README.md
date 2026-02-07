## Aston - Service Orchestration

Проект содержит Docker-оркестрацию для микросервисной системы.

Это RESTful Spring Boot приложение для работы с базой пользователей. User-service предоставляет стандартный CRUD-функционал, notification-service отправляет уведомления на email. Между собой они связаны через Kafka. 

Единый интерфейс реализован через API Gateway в связке с Discovery Service, конфигурация - через Config Server. 




---

### 🚀 Быстрый старт
```shell
mkdir aston && cd aston
git clone https://github.com/gedfalk/aston-serviceOrchestration.git
git clone https://github.com/gedfalk/aston-project.git
git clone https://github.com/gedfalk/aston-notificationProject.git
git clone https://github.com/gedfalk/aston-discoveryServer.git
git clone https://github.com/gedfalk/aston-configServer.git
git clone https://github.com/gedfalk/aston-apiGateway.git

cd aston-serviceOrchestration 
docker-compose up --build
```
---

### 📡 Проверка

 - Discovery Service - http://localhost:8761
 - Config Server - http://localhost:8888/user-service/default
 - API Gateway - http://localhost:8080/user/api/users
 - Kafka-ui - http://localhost:8081
---

### 📡 Пример API-запроса
```shell
curl -X POST http://localhost:8080/user/api/users \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Eugene Me",
    "email": "somemail@gmail.com",
    "age": 30
  }'
```

