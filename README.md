# Reservas Canchas MS Auth

Authentication microservice for the sports field reservation system.

## Description

This service manages authentication and authorization features, including:

- user registration
- admin registration
- login
- JWT token generation
- user persistence in MongoDB

## Tech Stack

- Java 17
- Spring Boot 3
- Spring Security
- MongoDB
- JWT
- Docker

## Project Structure

```text
src/
.mvn/
Dockerfile
pom.xml
mvnw
mvnw.cmd
HELP.md
README.md
````

## Run Locally

```bash id="6yz0gu"
./mvnw spring-boot:run
```

On Windows:

```powershell id="vdkhly"
.\mvnw.cmd spring-boot:run
```

## Build

```bash id="zw3kvl"
./mvnw clean package -DskipTests
```

On Windows:

```powershell id="dglyco"
.\mvnw.cmd clean package -DskipTests
```

## Docker

This project uses a runtime Dockerfile that expects the jar file to exist in `target/`.

Example workflow:

```powershell id="8uxn2g"
.\mvnw.cmd clean package -DskipTests
docker build -t reservas-canchas-ms-auth .
```

## Environment Variables

* `SERVER_PORT`
* `MONGODB_URI`
* `JWT_SECRET`

## Main Endpoints

Examples of available endpoints:

* `/auth/register`
* `/auth/register-admin`
* `/auth/login`

## Notes

* This service must use the same `JWT_SECRET` as the gateway within the same environment.
* Users are stored in MongoDB.
* Generated tokens are later validated by the gateway.

## Related Repositories

* `reservas-canchas-gateway`
* `reservas-canchas-ms-reservas`
* `reservas-canchas-infra`

