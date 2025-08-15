# Student Registration Portal - Frontend

This is the React-based frontend for the Student Registration Portal. It provides a user-friendly interface for students and admins to manage student records.

---

## Technologies Used

- **React** (with Create React App or Vite)
- **JavaScript/TypeScript**
- **Axios** (for API calls)
- **Bootstrap/Material-UI** (for UI styling, if used)

---

## Features

- Login for normal users and admin users
- Admin-only features: Import CSV, Edit, Delete, Add Student
- Normal users can view student records and search/filter
- Export student data to CSV and PDF
- Filter students by college and branch/class
- Responsive UI with notifications
- Logout option for both user types
- Role-based UI: "Login as Admin" button for normal users
- Form validation for mobile (10 digits, numbers only) and aadhar (16 digits, numbers only)

---

## Step-by-Step Installation and Setup


### 1. Prerequisites

#### Install Node.js and npm (Step-by-Step)

Node.js is required to run the frontend. npm (Node Package Manager) comes bundled with Node.js.

**Step 1: Check if Node.js and npm are already installed**
```
node -v
npm -v
```
If you see version numbers, Node.js and npm are already installed. If not, follow the steps below.

**Step 2: Download Node.js**

- Go to the [Node.js official website](https://nodejs.org/).
- Download the LTS (Long Term Support) version for your operating system (Windows, macOS, or Linux).

**Step 3: Install Node.js**

- Run the downloaded installer and follow the prompts to complete the installation.
- On Windows, accept the license agreement, choose the installation path, and proceed with the default options.
- On Linux, you can also use a package manager. For example, on Ubuntu:
	```bash
	sudo apt update
	sudo apt install -y nodejs npm
	```
	Or on RHEL/CentOS:
	```bash
	sudo dnf install -y nodejs npm
	```

**Step 4: Verify Installation**
```
node -v
npm -v
```
You should see version numbers for both Node.js and npm.

---

---

### 2. Clone the Frontend Repository

Navigate to your desired directory and clone the repository:
```
git clone https://github.com/Nareshindu/Student-portal-frontend.git
cd Student-portal-frontend
```

---

### 3. Install Dependencies

Install all required npm packages:
```
npm install
```

---

### 4. Configure Environment Variables (Optional)

If your backend API endpoint is different from the default, create a `.env` file in the project root and add:
```
REACT_APP_API_URL=http://<backend-ip>:8080
```
Replace `<backend-ip>` with your backend server's IP address or domain.

---

### 5. Start the Development Server

Run the following command to start the frontend in development mode:
```
npm start
```
The application will be available at `http://localhost:3000` by default.

---

### 6. Build for Production

To create an optimized production build:
```
npm run build
```
The build output will be in the `build/` directory.

---

## Folder Structure

- `src/components/` - React components (HomePage, AddStudentForm, EditStudentForm, etc.)
- `src/services/` - API service for backend communication
- `public/` - Static assets

---

## Usage

- Normal users can view and search student records.
- Admin users can add, edit, delete, and import students via CSV.
- Use the "Login as Admin" button to switch roles.

---

## Notes

- Ensure the backend server is running and accessible at the API URL specified in your `.env` file or in the code.
- For production deployment, serve the `build/` directory using a static server or integrate with your backend server.

---
