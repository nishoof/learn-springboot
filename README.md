# learn-springboot

> CRUD backend in SpringBoot

Uses PostgreSQL as the database with Hibernate and Spring Data JPA.

## Setup

This is a Maven project.

PostgreSQL should be installed and running.

1. Create the database:
   ```sql
   CREATE DATABASE student;
   ```

2. (Optional) Configure database credentials:
   If your PostgreSQL requires authentication, edit `src/main/resources/application.properties`:
   ```properties
   spring.datasource.username=your_username
   spring.datasource.password=your_password
   ```

3. Start the application:
   ```bash
   ./mvnw spring-boot:run
   ```
   The application will run on http://localhost:8080. Or you can specify a different port:
   ```bash
   ./mvnw spring-boot:run -Dspring-boot.run.arguments="--server.port=8081"
   ```

## API Endpoints

- `GET /api/v1/student` - Get all students
- `POST /api/v1/student` - Add new student (with JSON body containing name, email, and dob)
- `PUT /api/v1/student/{id}` - Update student (with query params for name and email)
- `DELETE /api/v1/student/{id}` - Delete student

Can be tested using Postman or whatever you want.

## Files

Going into src/main/java/com/example/demo the main method is in DemoApplication.java. The rest of the code is in the student folder.
- **Student.java**: POJO defining a student
- **StudentConfig.java**: Just creates 2 initial students and saves them to the database
- **StudentController.java**: RestController that exposes REST API endpoints for CRUD operations (GET all students, POST new student, PUT update student, DELETE student)
- **StudentRepository.java**: JPA Repository interface. Provides database operations. Used by the service layer
- **StudentService.java**: Service layer containing business logic for managing students. Used by the controller
