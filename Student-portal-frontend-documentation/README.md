# Student Registration Portal - Frontend

This is the React-based frontend for the Student Registration Portal. It provides a user-friendly interface for students and admins to manage student records.

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

## Getting Started
1. Install dependencies:
   ```bash
   npm install
   ```
2. Start the development server:
   ```bash
   npm start
   ```

## Folder Structure
- `src/components/` - React components (HomePage, AddStudentForm, EditStudentForm, etc.)
- `src/services/` - API service for backend communication
- `public/` - Static assets

## Environment
- Create a `.env` file for API endpoints if needed.

## Usage
- Normal users can view and search student records.
- Admin users can add, edit, delete, and import students via CSV.
- Use the "Login as Admin" button to switch roles.

---
