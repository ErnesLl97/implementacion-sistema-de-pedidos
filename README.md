# Sistema de Pedidos

Este proyecto es una aplicación didáctica que implementa un sistema básico de pedidos usando una arquitectura de microservicios

---

## Tecnologías usadas

- **Java **
- **Spring Boot** (REST API, Spring Data JPA, Spring Kafka)
- **Apache Kafka** (mensajería asincrónica)
- **MySQL** (base de datos relacional)
- **Docker** (contenedores para base de datos y Kafka)
- **Swagger/OpenAPI** (documentación API)
- **Lombok** (reducción de boilerplate)
- **Maven** (gestión de dependencias)

---

## Arquitectura y descripción

El sistema consta de dos microservicios principales:

1. **pedido-service**  
   - Servicio productor de pedidos.  
   - Expone un endpoint para crear pedidos.  
   - Envía pedidos a un topic Kafka (`pedidos`).  

2. **procesador-service**  
   - Servicio consumidor de pedidos.  
   - Escucha el topic Kafka y persiste pedidos en MySQL.  
   - Expone endpoints para consultar pedidos (listado y detalle).  
   

---

## Cómo ejecutar

1. Clona el repositorio.
2. Asegúrate de tener Docker y Docker Compose instalados.
3. Ejecuta `docker-compose up` para levantar Kafka, Zookeeper y MySQL.
4. Ejecuta los microservicios `pedido-service` y `procesador-service` desde tu IDE o línea de comandos.
5. Prueba los endpoints con Postman o Swagger UI.

---

## Endpoints destacados

### pedido-service
- `POST /api/pedidos` – Crear un pedido (envía mensaje Kafka).

### procesador-service
- `GET /pedidos` – Listar todos los pedidos.
- `GET /pedidos/{id}` – Obtener pedido por ID.



