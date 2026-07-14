
# EMS — Employee Management System 🏢

EMS is a full-stack MERN Employee Management System with role-based access for Admins and Employees. It handles employee records, attendance (clock in/out), leave applications, and payslips, with automated email reminders powered by background jobs.

# Features


🔐 Role-Based Authentication — JWT-based login with ADMIN and EMPLOYEE roles, plus secure password change
👥 Employee Management — Admins can create, update, and remove employee records (department, position, salary, status)
🕒 Attendance Tracking — Employees clock in/out; status auto-calculated (Present, Late, Absent) with working hours and day type
🌴 Leave Management — Employees apply for leave (Sick, Casual, Annual); admins approve or reject requests
💵 Payslip Generation — Admins generate monthly payslips with basic salary, allowances, deductions, and net salary; employees view/print their own
📊 Dashboard — Role-specific overview of key stats for admins and employees
👤 Profile Management — Employees can view and update their own profile
📧 Automated Email Reminders — Background jobs (Inngest) send check-out reminders, leave-approval reminders, and a daily cron alert for employees who haven't marked attendance
🌱 Admin Seeding — One-command script to create the first admin account


# Tech Stack

# Frontend (/client)


React 19
Vite
Tailwind CSS v4
React Router v7
Axios
date-fns
Lucide React (icons)
React Hot Toast (notifications)


# Backend (/server)


Node.js
Express 5
MongoDB
Mongoose (ODM)
JSON Web Tokens (auth)
bcrypt (password hashing)
Inngest (background jobs & cron reminders)
Nodemailer (transactional email)
Multer (form-data parsing)


# Setup

# Server

bashcd server
npm install

Create server/.env:

envJWT_SECRET=your_jwt_secret
ADMIN_EMAIL=your_admin_email

MONGODB_URI=your_mongodb_uri

INNGEST_EVENT_KEY=your_inngest_event_key
INNGEST_SIGNING_KEY=your_inngest_signing_key

SMTP_USER=your_smtp_user
SMTP_PASS=your_smtp_password
SENDER_EMAIL=your_sender_email

Create the first admin account (uses ADMIN_EMAIL above, temporary password admin123):

bashnpm run seed

Run the server:

bashnpm run server

Client

bashcd client
npm install

Create client/.env:

envVITE_BASE_URL=http://localhost:4000

bashnpm run dev


Start the server first — the client depends on it.

- admin credentials- admin@example.com 
- password-admin123

