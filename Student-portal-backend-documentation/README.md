# Student Registration Portal - Backend

This is the Spring Boot backend for the Student Registration Portal. It provides RESTful APIs for managing student records and authentication.

---

## Technologies Used

- **Java 1.8+**
- **Spring Boot**
- **Maven**
- **PostgreSQL**
- **Spring Data JPA**
- **Spring Security**

---

## Features

- Student CRUD operations (Create, Read, Update, Delete)
- Bulk import of students via CSV
- Role-based access: admin and normal user
- Admin-only endpoints for add, edit, delete, and import
- Data validation for mobile (10 digits, numbers only) and aadhar (16 digits, numbers only)
- Secure login and session management
- Error handling and notifications

---

## Prerequisites

- **Java 1.8 or above**
- **Maven 3.6+**
- **PostgreSQL**

---

## Installation Steps

### 1. Install Java (JDK 8+)

On RHEL:
```
sudo dnf install -y java-1.8.0-openjdk java-1.8.0-openjdk-devel
```
Verify:
```
java -version
```

Set JAVA_HOME in `~/.bashrc` or `/etc/profile.d/java.sh`:
```
export JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk
export PATH=$JAVA_HOME/bin:$PATH
```
Reload:
```
source ~/.bashrc
# or
source /etc/profile.d/java.sh
```

---

### 2. Install Maven

Manual installation:
```
cd /opt
sudo wget https://archive.apache.org/dist/maven/maven-3/3.9.6/binaries/apache-maven-3.9.6-bin.tar.gz
sudo tar -xvzf apache-maven-3.9.6-bin.tar.gz
sudo mv apache-maven-3.9.6 apache-maven
```
Set Maven environment variables in `/etc/profile.d/maven.sh`:
```
export M2_HOME=/opt/apache-maven
export PATH=${M2_HOME}/bin:${PATH}
```
Reload:
```
source /etc/profile.d/maven.sh
```
Verify:
```
mvn -version
```
Or install via yum:
```
sudo yum install maven
```

---

### 3. Configure PostgreSQL

Install PostgreSQL client:
```
sudo dnf install -y postgresql13
```
Verify:
```
psql --version
```
Test connection:
```
psql -h <db-ip> -U <username> -d <dbname>
```

---

### 4. Download and Configure the Application

Clone the repository:
```
sudo git clone https://github.com/Nareshindu/Student-code.git /opt/Student-code
sudo chown -R ec2-user:ec2-user /opt/Student-code
```
Edit database configuration:
```
sudo vi /opt/Student-code/StudentManagementSystem/src/main/resources/application.properties
```
Update:
```
spring.datasource.url=jdbc:postgresql://<DB_IP>:5432/student_details
spring.datasource.username=<username>
spring.datasource.password=<password>
```

---

### 5. Build and Run the Backend

```
cd /opt/Student-code/StudentManagementSystem
mvn clean install
mvn spring-boot:run
```

---

## Folder Structure

- `src/main/java/com/sms/` - Main application and packages
  - `controller/` - REST controllers
  - `entity/` - JPA entities
  - `repository/` - Spring Data repositories
  - `service/` - Business logic
- `src/main/resources/` - Application properties

---

## API Endpoints

- `/students` - Get all students
- `/students/{id}` - Get, update, or delete a student
- `/students/import` - Bulk import students (admin only)
- `/login` - User/admin authentication

---

## Example Credentials

- **Admin:**
  - Username: `admin`
  - Password: `admin123`
- **User:**
  - Username: `user`
  - Password: `user123`

---

## Usage

- Connect the frontend to the backend API endpoints
- Use admin credentials for full access

---
