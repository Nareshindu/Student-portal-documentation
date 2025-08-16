# Student Registration Portal - Frontend

This is the React-based frontend for the Student Registration Portal. It provides a user-friendly interface for students and admins to manage student records.

---

##  Technologies Used

- **React** (via Create React App)
- **JavaScript**
- **Axios** – HTTP client for API calls
- **Bootstrap / Material-UI** – UI Styling (optional)
- **Node.js + npm** – Runtime and package manager

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

## Step-by-Step Installation & Deployment


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
```
curl -fsSL https://rpm.nodesource.com/setup_18.x | sudo bash -
sudo yum install -y nodejs
```
Or for Ubuntu:
```
curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
sudo apt install -y nodejs
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
cd /opt
sudo git clone https://github.com/Nareshindu/Student-portal-frontend.git
sudo chown -R ec2-user:ec2-user /opt/Student-portal-frontend
cd /opt/Student-portal-frontend/Student-portal-frontend

```

---

### 3. Install Dependencies(When you are running npm install command you should run this command where package.json is there )

Install all required npm packages:
```
npm install
```

---


### 4. Configure Environment Variables (Optional)

If your backend API endpoint is different from the default, create a `.env` file in the project root directory (the same directory as your `package.json`).

**Path:**
```
sudo vi /opt/Student-portal-frontend/Student-portal-frontend/src/services/StudentService.js
```
REACT_APP_API_URL=http://<backend-ip>:8080
```
Replace `<backend-ip>` with your backend server's IP address or domain.

---


### 6. Build for Production

To create an optimized production build:
```
npm run build
```
The build output will be in the `build/` directory.

---

### 7. Serve the Production Build with a Systemd Service (Optional)

To serve the frontend in production, you can use a static file server like `serve` (Node.js) or Nginx. Below is an example using the `serve` package and systemd:

**Step 1: Install the serve package globally**
```
sudo npm install -g serve
```

**Step 2: Create a systemd service file**
```
sudo vi /etc/systemd/system/frontend.service
```
Paste the following content (update paths as needed):
```
[Unit]
Description=React Frontend Service
After=network.target

[Service]
Type=simple
User=ec2-user
WorkingDirectory=/opt/Student-portal-frontend/Student-portal-frontend
ExecStart=/usr/bin/serve -s build -l 3000
Restart=always
RestartSec=5
SyslogIdentifier=react-frontend

[Install]
WantedBy=multi-user.target
```

**Step 3: Reload systemd and start the service**
```
sudo systemctl daemon-reload
sudo systemctl enable frontend
sudo systemctl start frontend
```

**Step 4: Check the status of the service**
```
sudo systemctl status frontend
```

Your frontend will now be served on port 3000 and managed by systemd.

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
