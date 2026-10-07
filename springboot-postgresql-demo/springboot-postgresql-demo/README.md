# Spring Boot + PostgreSQL Demo

## Technologies
- Java 17
- Spring Boot 3.5.6
- Spring Web
- Spring Data JPA
- PostgreSQL Driver
- Maven

## 1. Create PostgreSQL database

Open pgAdmin or psql and run:

```sql
CREATE DATABASE springboot_db;
```

## 2. Configure PostgreSQL password

Open:

`src/main/resources/application.properties`

Change:

```properties
spring.datasource.password=YOUR_POSTGRES_PASSWORD
```

to your actual PostgreSQL password.

## 3. Run the project

From the project root:

```bash
mvn spring-boot:run
```

Or run `SpringbootPostgresqlDemoApplication.java` from Eclipse/IntelliJ.

## 4. Test APIs

### Get all users
GET http://localhost:8080/api/users

### Create user
POST http://localhost:8080/api/users

JSON:
```json
{
  "name": "Janhavi",
  "email": "janhavi@example.com"
}
```

### Get user by ID
GET http://localhost:8080/api/users/1

### Delete user
DELETE http://localhost:8080/api/users/1

The `users` table will be created automatically by Hibernate because:

```properties
spring.jpa.hibernate.ddl-auto=update
```
