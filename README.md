# jpa-demo

Build with
```
mvn clean package
```

Run locally 

```
**java -jar ./target/demo-0.0.1-SNAPSHOT.jar**


  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::                (v2.6.4)

2022-03-04 11:00:19.684  INFO 21142 --- [           main] com.example.demo.JpaDemoApplication      : Starting JpaDemoApplication v0.0.1-SNAPSHOT using Java 11.0.14 on bmullan-a02.vmware.com with PID 21142 (/Users/bmullan/Downloads/demo/target/demo-0.0.1-SNAPSHOT.jar started by bmullan in /Users/bmullan/Downloads/demo)
2022-03-04 11:00:19.687  INFO 21142 --- [           main] com.example.demo.JpaDemoApplication      : No active profile set, falling back to 1 default profile: "default"
2022-03-04 11:00:20.249  INFO 21142 --- [           main] .s.d.r.c.RepositoryConfigurationDelegate : Bootstrapping Spring Data JPA repositories in DEFAULT mode.
2022-03-04 11:00:20.300  INFO 21142 --- [           main] .s.d.r.c.RepositoryConfigurationDelegate : Finished Spring Data repository scanning in 42 ms. Found 1 JPA repository interfaces.
2022-03-04 11:00:20.874  INFO 21142 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port(s): 8080 (http)
2022-03-04 11:00:20.885  INFO 21142 --- [           main] o.apache.catalina.core.StandardService   : Starting service [Tomcat]
2022-03-04 11:00:20.886  INFO 21142 --- [           main] org.apache.catalina.core.StandardEngine  : Starting Servlet engine: [Apache Tomcat/9.0.58]
2022-03-04 11:00:20.939  INFO 21142 --- [           main] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2022-03-04 11:00:20.939  INFO 21142 --- [           main] w.s.c.ServletWebServerApplicationContext : Root WebApplicationContext: initialization completed in 1195 ms
2022-03-04 11:00:21.129  INFO 21142 --- [           main] com.zaxxer.hikari.HikariDataSource       : HikariPool-1 - Starting...
2022-03-04 11:00:21.275  INFO 21142 --- [           main] com.zaxxer.hikari.HikariDataSource       : HikariPool-1 - Start completed.
2022-03-04 11:00:21.327  INFO 21142 --- [           main] o.hibernate.jpa.internal.util.LogHelper  : HHH000204: Processing PersistenceUnitInfo [name: default]
2022-03-04 11:00:21.370  INFO 21142 --- [           main] org.hibernate.Version                    : HHH000412: Hibernate ORM core version 5.6.5.Final
2022-03-04 11:00:21.511  INFO 21142 --- [           main] o.hibernate.annotations.common.Version   : HCANN000001: Hibernate Commons Annotations {5.1.2.Final}
2022-03-04 11:00:21.621  INFO 21142 --- [           main] org.hibernate.dialect.Dialect            : HHH000400: Using dialect: org.hibernate.dialect.H2Dialect
**2022-03-04 11:00:22.114  INFO 21142 --- [           main] o.h.t.schema.internal.SchemaCreatorImpl  : HHH000476: Executing import script 'jar:file:/Users/bmullan/Downloads/demo/target/demo-0.0.1-SNAPSHOT.jar!/BOOT-INF/classes!/import.sql'
**2022-03-04 11:00:22.117  INFO 21142 --- [           main] o.h.e.t.j.p.i.JtaPlatformInitiator       : HHH000490: Using JtaPlatform implementation: [org.hibernate.engine.transaction.jta.platform.internal.NoJtaPlatform]
2022-03-04 11:00:22.124  INFO 21142 --- [           main] j.LocalContainerEntityManagerFactoryBean : Initialized JPA EntityManagerFactory for persistence unit 'default'
2022-03-04 11:00:22.192  WARN 21142 --- [           main] JpaBaseConfiguration$JpaWebConfiguration : spring.jpa.open-in-view is enabled by default. Therefore, database queries may be performed during view rendering. Explicitly configure spring.jpa.open-in-view to disable this warning
2022-03-04 11:00:23.220  INFO 21142 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''
2022-03-04 11:00:23.229  INFO 21142 --- [           main] com.example.demo.JpaDemoApplication      : Started JpaDemoApplication in 3.973 seconds (JVM running for 4.417)


```


Invoke (GET)

```
 % curl localhost:8080/persons
{
  "_embedded" : {
    "persons" : [ {
      "firstName" : "Tony",
      "lastName" : "Stark",
      "_links" : {
        "self" : {
          "href" : "http://localhost:8080/persons/1"
        },
        "person" : {
          "href" : "http://localhost:8080/persons/1"
        }
      }
    }, {
```

Invoke (POST)
```
% curl -X POST -H 'Content-Type: application/json'  -d '{ "firstName" : "joe","lastName" : "biden" }' localhost:8080/persons
{
  "firstName" : "joe",
  "lastName" : "biden",
  "_links" : {
    "self" : {
      "href" : "http://localhost:8080/persons/3"
    },
    "person" : {
      "href" : "http://localhost:8080/persons/3"
    }
  }
}%
```


