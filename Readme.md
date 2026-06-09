# Discovery Server (Eureka)

Service registry and discovery server. All microservices register here and discover each other.

## Tech Stack

- Java 21 · Spring Boot · Spring Cloud Netflix Eureka

## Quick Start

```powershell
.\gradlew.bat bootRun
```

Eureka dashboard: http://localhost:8761

## Configuration

```yaml
server:
  port: 8761

spring:
  application:
    name: eureka-server

eureka:
  client:
    register-with-eureka: false
    fetch-registry: false
```

Port 8761 is hardcoded in all services. Don't change it.

## How It Works

1. Start discovery server first
2. All microservices connect to `http://host.docker.internal:8761/eureka/` on startup
3. Services register themselves with unique names (product-service, order-service, etc.)
4. Services query registry to find and call other services by name

## Dashboard

Visit http://localhost:8761 to see:
- Registered services
- Service instances
- Health status

## Tests

```powershell
.\gradlew.bat test
```

## Status

✅ Eureka server running
✅ Service registration
✅ Service discovery
✅ Dashboard UI

