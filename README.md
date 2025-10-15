# 📩 Service Notification

Microserviço responsável por enviar notificações para usuários do sistema **MyMicroservice**.

---

## ⚙️ Funções
- Receber notificações via POST `/notification`  
- Integrar-se com `service-tasks` para envio automático de alertas de tarefas  
- Registrar-se no Eureka para que outros serviços possam encontrá-lo  

---

## 📌 Propriedades importantes

```properties
spring.application.name=service-notification
server.port=8082
spring.cloud.config.uri=http://service-main:8888/config
spring.config.import=configserver:http://service-main:8888/config
eureka.client.serviceUrl.defaultZone=http://service-main:8888/eureka
eureka.instance.hostname=service-notification
```
## 🚀 Executando localmente
```
mvn spring-boot:run
```
## Endpoint para envio de notificações:
```
POST http://localhost:8082/notification
```
- Corpo JSON:
```

{
  "message": "Sua tarefa está próxima do prazo",
  "email": "usuario@email.com"
}
```
## 🔗 Dependências

- Config Server (service-main)

- Eureka Server (service-main)

- Recebe requisições do service-tasks
