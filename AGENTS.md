# Demo Supermarket

- This is a Java 25, Maven, Spring Boot application. Use the Maven Wrapper: `./mvnw test` for unit tests and `./mvnw verify` when end-to-end coverage is required.
- Keep application code under `src/main/java/demo/supermarket`, organized by feature (`catalog`, `cart`, `security`). Place matching tests under `src/test/java/demo/supermarket`.
- The UI is server-rendered with Thymeleaf templates in `src/main/resources/templates` and HTMX. Preserve controller/template contracts and test user-visible behavior.
- Persisted schema changes require a new, forward-only Flyway migration in `src/main/resources/db/migration`; never edit an applied migration.
- H2 is the runtime database. Treat cart token generation, quantity validation, and cart updates as concurrency-sensitive; retain focused service and controller tests for changes there.
- Keep security configuration and public routes explicit. Do not broaden access as an incidental part of a feature change.
