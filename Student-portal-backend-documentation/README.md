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

## Step-by-Step Installation and Setup

### 1. Install Java 8 (OpenJDK 1.8)

Java is required to run the backend. On RHEL-based systems, install Java 8 using:
```
sudo dnf install -y java-1.8.0-openjdk java-1.8.0-openjdk-devel
```
**Verify the installation:**
```
java -version
```
You should see output showing Java 1.8 is installed.

**Set JAVA_HOME Environment Variable:**
Add the following lines to your `~/.bashrc` or `/etc/profile.d/java.sh` file:
```
export JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk
export PATH=$JAVA_HOME/bin:$PATH
```
Reload the file to apply changes:
```
source ~/.bashrc
# or
source /etc/profile.d/java.sh
```

---

### 2. Install Apache Maven

Maven is used to build and manage the project dependencies.

**Manual Installation:**
```
cd /opt
sudo wget https://archive.apache.org/dist/maven/maven-3/3.9.6/binaries/apache-maven-3.9.6-bin.tar.gz
sudo tar -xvzf apache-maven-3.9.6-bin.tar.gz
sudo mv apache-maven-3.9.6 apache-maven
```
**Set Maven Environment Variables:**
Create or edit `/etc/profile.d/maven.sh` and add:
```
export M2_HOME=/opt/apache-maven
export PATH=${M2_HOME}/bin:${PATH}
```
Reload:
```
source /etc/profile.d/maven.sh
```
**Verify Maven Installation:**
```
mvn -version
```
You should see Maven version output.

**Alternative (YUM):**
```
sudo yum install maven
```

---
### 3. Download and Configure the Application

**Clone the repository:**
```
sudo git clone https://github.com/Nareshindu/Student-portal-backend.git 
cd /opt/Student-portal-backend
sudo chown -R ec2-user:ec2-user /opt/Student-portal-backend
```

**Edit database configuration:**
Open the application properties file:
```
sudo vi /opt/Student-portal-backend/src/main/resources/application.properties
```
Update the following lines with your database details:
```
spring.datasource.url=jdbc:postgresql://<DB_IP>:5432/student_details
spring.datasource.username=<username>
spring.datasource.password=<password>
```
Replace `<DB_IP>`, `<username>`, and `<password>` with your actual PostgreSQL server details.

---

### 4. Build and Run the Backend

Navigate to the project directory and build the application:
```
cd /opt/Student-portal-backend/
mvn clean install
```
After a successful build, run the backend:
```
mvn spring-boot:run
```
The backend will start on the default port (usually 8080).

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
