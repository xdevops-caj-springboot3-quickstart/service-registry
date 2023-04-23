# Service registry

Service registry via Eureka server.

## How to include and run a Eureka server

### Import dependencies

```xml
<dependency>
    <groupId>org.springframework.cloud</groupId>
    <artifactId>spring-cloud-starter-netflix-eureka-server</artifactId>
</dependency>
```

### Enable Eureka server

Add `@EnableEurekaServer` annotation for the Spring Boot application class.

### Configure Eureka server

```yaml
server:
  port: 8761

eureka:
  instance:
    hostname: localhost
  client:
    registerWithEureka: false
    fetchRegistry: false
    serviceUrl:
      defaultZone: http://${eureka.instance.hostname}:${server.port}/eureka/
```

## Run application

```bash
mvn spring-boot:run
```

or run the Spring Boot application directly.

## Access Eureka server dashboard

Access <http://localhost:8761/> in browser.


## References

- https://cloud.spring.io/spring-cloud-netflix/reference/html/#spring-cloud-eureka-server