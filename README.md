# Spring Boot with REST and MySQL

This API exposes GET/POST/PUT/DELETE end-points for user model.

## Create table

Set your database credentials in application.properties file and create table

```sh
CREATE TABLE `product` (
  `id` bigint(20) NOT NULL AUTO_INCREMENT,
  `created_at` datetime(6) DEFAULT NULL,
  `description` varchar(255) DEFAULT NULL,
  `name` varchar(255) DEFAULT NULL,
  `price` decimal(19,2) DEFAULT NULL,
  `updated_at` datetime(6) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB
```

## Run app

```sh
mvn clean spring-boot:run
```

## Hit end-points

POST data

```sh
curl -H "Content-Type: application/json" -X POST -d '{"name":"widget","description": "blue and thingy","price":"1"}' http://localhost:8080/api/v1/products
```

GET products

```sh
curl http://localhost:8080/api/v1/products
```

Swagger UI is at <http://localhost:8080/swagger-ui.html>