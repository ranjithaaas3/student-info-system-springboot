# Student Information Management System (Spring Boot + MySQL)

[👤 Profile: @ranjithaaas3](https://github.com/ranjithaaas3)

A backend project to manage student records with CRUD, search, and basic authentication.

## Features
- Create/Read/Update/Delete students, courses, and enrollments
- Search by name, course, date range
- JWT-based auth (optional milestone)
- Validation & exception handling

## Tech
Spring Boot, Java, MySQL, JPA/Hibernate, Maven, JUnit

## Getting Started

### 1) Clone & open
```bash
git clone https://github.com/ranjithaaas3/student-info-system-springboot.git
cd student-info-system-springboot
```

### 2) Create database
```sql
CREATE DATABASE studentdb;
CREATE USER 'studentuser'@'localhost' IDENTIFIED BY 'studentpass';
GRANT ALL PRIVILEGES ON studentdb.* TO 'studentuser'@'localhost';
FLUSH PRIVILEGES;
```

### 3) Configure `src/main/resources/application.properties`
```
spring.datasource.url=jdbc:mysql://localhost:3306/studentdb
spring.datasource.username=studentuser
spring.datasource.password=studentpass
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

### 4) Run
```bash
./mvnw spring-boot:run
```

### 5) API (sample)
- `GET /api/students`
- `GET /api/students/{id}`
- `POST /api/students`
- `PUT /api/students/{id}`
- `DELETE /api/students/{id}`

### 6) Tests
```bash
./mvnw test
```

## Project Structure
```
src/
  main/java/.../controller
  main/java/.../service
  main/java/.../repository
  main/java/.../model
  test/java/... (JUnit tests)
```

## CI (GitHub Actions) — optional
Create `.github/workflows/maven.yml`:
```yaml
name: Java CI
on: [push, pull_request]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-java@v4
        with:
          distribution: temurin
          java-version: '21'
      - run: ./mvnw -q -DskipTests=false test
```
