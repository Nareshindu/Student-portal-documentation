# Student Registration Portal - Backend

This is the Spring Boot backend for the Student Registration Portal. It provides RESTful APIs for managing student records and authentication.

## Features
- Student CRUD operations (Create, Read, Update, Delete)
- Bulk import of students via CSV
- Role-based access: admin and normal user
- Admin-only endpoints for add, edit, delete, and import
- Data validation for mobile (10 digits, numbers only) and aadhar (16 digits, numbers only)
- Secure login and session management
- Error handling and notifications

## Getting Started
1. Install Java (JDK 8+)
2. Install Maven
3. Build and run the backend:
   ```bash
   mvn clean install
   mvn spring-boot:run
   ```

## Folder Structure
- `src/main/java/com/sms/` - Main application and packages
  - `controller/` - REST controllers
  - `entity/` - JPA entities
  - `repository/` - Spring Data repositories
  - `service/` - Business logic
- `src/main/resources/` - Application properties

## API Endpoints
- `/students` - Get all students
- `/students/{id}` - Get, update, or delete a student
- `/students/import` - Bulk import students (admin only)
- `/login` - User/admin authentication

## Example Credentials
- **Admin:**
  - Username: `admin`
  - Password: `admin123`
- **User:**
  - Username: `user`
  - Password: `user123`

## Usage
- Connect the frontend to the backend API endpoints
- Use admin credentials for full access

---
