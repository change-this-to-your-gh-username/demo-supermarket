# Demo Supermarket

- This is a Java 25, Maven, Spring Boot 4 application. Use the Maven wrapper: `./mvnw test` for unit and MVC tests, `./mvnw verify` for the full build including Playwright end-to-end tests, and `./mvnw spring-boot:run` to run locally.
- Application code is under `src/main/java/demo/supermarket`, organised by feature (`cart`, `catalog`, `security`). Keep controllers thin; put business rules in services and persistence access in repositories.
- The UI is server-rendered Thymeleaf with htmx. Keep templates in `src/main/resources/templates` and static assets in `src/main/resources/static`; preserve endpoint/template fragment contracts when changing interactions.
- Data uses H2 in PostgreSQL compatibility mode with Flyway and JPA validation. Add schema changes as a new, ordered migration in `src/main/resources/db/migration`; never edit an applied migration.
- Add or update focused tests in `src/test/java`. Normal tests run under Surefire; browser tests are tagged `e2e` and run through Failsafe during `verify`.
- Security configuration deliberately controls public routes. Update `SecurityConfiguration` and its route tests together when adding or changing HTTP endpoints.
