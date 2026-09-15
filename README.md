# ⚡ CampusForge — College Complaint Management System

> **Premium • Futuristic • Instant**

CampusForge is a modern **College Complaint Management System** designed to simplify the process of submitting, tracking, managing, and resolving campus-related complaints.

The system provides different interfaces for **Students, Teachers, Maintenance Admins, and Super Admins**, allowing complaints to be handled through a centralized digital platform.

---

## 📌 Project Overview

In traditional college complaint systems, students may need to physically approach departments, submit written complaints, or repeatedly follow up to know the status of an issue.

**CampusForge** provides a digital solution where students can:

* Submit complaints online
* Add detailed descriptions
* Upload supporting photographs
* Use voice input
* View complaint status
* Communicate through live discussion
* Receive official responses
* Access announcements
* Use the interface in English, Hindi, and Marathi

Administrative users can view complaints, update their status, respond to students, manage users, publish announcements, and suspend users for misuse.

---

## 🎯 Objectives

The main objectives of CampusForge are:

1. To digitize the college complaint management process.
2. To provide students with an easy complaint submission platform.
3. To allow students to track the progress of complaints.
4. To help teachers and maintenance staff manage complaints efficiently.
5. To provide administrators with analytics and user-management features.
6. To support multilingual interaction.
7. To provide voice-based complaint input.
8. To improve communication between students and college authorities.

---

## 👥 User Roles

CampusForge supports four different roles.

### 👨‍🎓 Student

Students can:

* Login using their Student ID
* View their dashboard
* Submit complaints
* Select a complaint department
* Add descriptions
* Upload photographs
* Use voice input
* Translate complaint text
* View submitted complaints
* Check complaint status
* Participate in complaint discussions

### 👨‍🏫 Teacher

Teachers can:

* Access the dashboard
* View all complaints
* Open complaint details
* Update complaint status
* Add official responses
* Participate in complaint discussions
* View announcements

### 🔧 Maintenance Admin

Maintenance administrators can:

* View maintenance-related complaints
* Review complaint details
* Update complaint status
* Add responses
* Communicate with students
* View campus announcements

### 👨‍💼 Super Admin

The Super Admin has the highest level of access and can:

* View all complaints
* Access analytics
* Manage users
* Suspend students
* Post system-wide announcements
* Update complaint statuses
* Add official responses
* Demonstrate different user roles

---

## 🛠️ Technologies Used

| Technology           | Purpose                            |
| -------------------- | ---------------------------------- |
| HTML5                | Website structure                  |
| CSS3                 | Custom styling and animations      |
| JavaScript           | Application logic and interactions |
| Tailwind CSS         | Responsive UI design               |
| Font Awesome         | Icons                              |
| Chart.js             | Charts and analytics               |
| Google Fonts         | Typography                         |
| Browser LocalStorage | Local data storage                 |
| Web Speech API       | Voice input                        |
| FileReader API       | Image upload and preview           |

---

## 🎨 UI/UX Design

CampusForge uses a futuristic **Glassmorphism** interface.

### Design Features

* Dark futuristic theme
* Neon blue visual identity
* Glass-effect cards
* Responsive layout
* Animated buttons
* Interactive status badges
* Modal-based complaint details
* Responsive dashboard
* Sidebar navigation
* Mobile-friendly structure

The primary visual theme uses a neon-blue accent to provide a modern technology-oriented appearance.

---

## 🔄 System Workflow

```text
                    ┌─────────────────────┐
                    │        User         │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   Select User Role  │
                    └──────────┬──────────┘
                               │
                 ┌─────────────┼─────────────┐
                 ▼             ▼             ▼
             Student        Teacher     Admin Roles
                 │             │             │
                 └─────────────┼─────────────┘
                               ▼
                    ┌─────────────────────┐
                    │      Dashboard      │
                    └──────────┬──────────┘
                               │
                     ┌─────────┴─────────┐
                     ▼                   ▼
              Submit Complaint      View Complaints
                     │                   │
                     ▼                   ▼
              Enter Description    Complaint Details
                     │                   │
          ┌──────────┼──────────┐        │
          ▼          ▼          ▼        │
       Voice      Translation   Photo     │
       Input       Support      Upload    │
          └──────────┼──────────┘        │
                     ▼                   │
              Moderation Check           │
                     │                   │
              ┌──────┴──────┐            │
              ▼             ▼            │
            Valid        Profanity       │
              │          Detected        │
              │             │            │
              ▼             ▼            │
          Save Data      Suspension      │
              │             │            │
              ▼             ▼            │
       Complaint Created  Logout         │
              │                          │
              └────────────┬─────────────┘
                           ▼
                    ┌───────────────┐
                    │ LocalStorage  │
                    └───────┬───────┘
                            ▼
                    ┌───────────────┐
                    │ Status Update │
                    └───────┬───────┘
                            ▼
                    ┌───────────────┐
                    │   Resolved    │
                    └───────────────┘
```

---

## 📂 Main Application Modules

### 1. Authentication Module

The login interface provides four role options:

* Student
* Teacher
* Maintenance Admin
* Super Admin

Students are validated using the format:

```text
BT24xxxx
```

Staff users use username and password fields.

---

### 2. Complaint Submission

Students can submit complaints by providing:

* Complaint title
* Department
* Description
* Date
* Optional image

The submitted complaint receives a unique complaint ID and starts with the status:

```text
Pending
```

---

### 3. Voice Input

The application uses the browser's **Speech Recognition API**.

The system can recognize speech based on the selected language:

```text
English → en-IN
Hindi   → hi-IN
Marathi → mr-IN
```

The recognized speech is automatically inserted into the complaint description.

---

### 4. Multilingual Support

CampusForge provides interface translations for:

* English
* Hindi
* Marathi

The translation system is implemented through JavaScript-based interface strings.

> **Note:** The current implementation uses simulated translation for complaint text rather than connecting to an external translation API.

---

### 5. Image Upload

Students can attach an image to their complaint.

The image is:

1. Selected from the device
2. Read using the FileReader API
3. Converted to Base64
4. Previewed on the form
5. Stored with the complaint data

---

### 6. Complaint Moderation

The system performs a basic profanity check before accepting a complaint.

A predefined list of inappropriate words is compared against the complaint description.

If inappropriate language is detected:

```text
Complaint
    ↓
Profanity Check
    ↓
Inappropriate Language?
    ↓
Yes
    ↓
Student Suspended for 20 Days
```

The suspension information is stored in LocalStorage.

---

## 📊 Complaint Status

Each complaint can have one of the following statuses:

| Status     | Meaning                      |
| ---------- | ---------------------------- |
| Pending    | Complaint has been submitted |
| Reviewing  | Complaint is being reviewed  |
| In Process | Action is being taken        |
| Solved     | Complaint has been resolved  |

---

## 💬 Live Discussion

Each complaint contains a discussion area where users can exchange messages.

Messages contain:

* User name
* Message
* Timestamp

The chat information is stored locally using browser LocalStorage.

---

## 📢 Announcements

The system includes a centralized announcement section.

Super Admin can publish announcements containing:

* Title
* Description
* Date
* Posted-by information

Announcements can then be viewed by authorized users.

---

## 📈 Analytics Dashboard

The Super Admin dashboard includes analytics such as:

* Total complaints
* Resolved complaints
* Pending complaints
* Department distribution
* Complaint trends

**Chart.js** is used to visualize complaint data.

---

## 👤 User Management

The Super Admin can view registered users and their:

* User ID
* Name
* Role
* Account status
* Suspension information

Students can also be manually suspended for 20 days by the administrator.

---

## 💾 Data Storage

The current application uses **Browser LocalStorage** for persistent demo data.

The following information is stored locally:

```text
campusforge_complaints
campusforge_announcements
campusforge_users
campusforge_current_user
```

This makes the application functional without requiring a separate database server for the current demo version.

---

## 🗂️ Project Structure

A recommended project structure is:

```text
CampusForge/
│
├── index.html
├── README.md
│
└── assets/
    └── images/
```

The current implementation can run as a single HTML file because the styling and JavaScript logic are embedded in the page.

---

## 🚀 How to Run

### Method 1 — Directly in Browser

1. Download or clone the repository.
2. Open the project folder.
3. Open `index.html` in a modern browser.
4. Select a user role.
5. Login and explore the dashboard.

### Method 2 — VS Code

1. Open the project in **Visual Studio Code**.
2. Open `index.html`.
3. Use **Live Server** if installed.
4. Open the generated localhost URL.
5. Explore the application.

---

## 🔐 Demo Login

### Student

```text
Student ID: BT241234
Password: Not Required
```

### Teacher

```text
Username: teacher01
Password: 123456
```

### Maintenance Admin

```text
Username: maint01
Password: 123456
```

### Super Admin

```text
Username: admin
Password: 123456
```

> These credentials are for demonstration purposes only and should not be used in a production system.

---

## 🌐 External Libraries

CampusForge uses the following external resources:

* Tailwind CSS CDN
* Font Awesome
* Chart.js
* Google Fonts

Internet access may therefore be required for all CDN-based features to load correctly.

---

## ⚠️ Current Limitations

This version is designed as a functional academic/demo project.

Current limitations include:

* Data is stored in browser LocalStorage.
* Authentication is demo-based.
* Passwords are not securely authenticated through a server.
* Translation is simulated.
* Complaint search/filter functionality is currently basic.
* There is no real-time cloud database.
* There is no production backend/API authentication.
* Analytics use demonstration/static chart values in some sections.

---

## 🔮 Future Scope

The system can be extended with:

* Node.js / Express backend
* MongoDB or MySQL database
* Secure authentication
* JWT-based authorization
* Real translation API
* AI/NLP-based complaint classification
* Automatic department assignment
* Email notifications
* SMS notifications
* Push notifications
* Real-time WebSocket chat
* Cloud image storage
* Advanced complaint analytics
* AI-powered complaint prioritization
* Automatic duplicate complaint detection
* Mobile application

---

## 🎓 Academic Project

**Project Name:** CampusForge — College Complaint Management System

**Project Type:** Web-Based Application

**Development Environment:** Visual Studio Code

**Frontend:** HTML, CSS, JavaScript, Tailwind CSS

**Visualization:** Chart.js

**Storage:** Browser LocalStorage

**Subject:** NLP / Academic Project

---

## 👩‍💻 Developer

**Samiksha Zodape**

JD College of Engineering and Management

---

## 📜 License

This project is developed for **educational and academic purposes**.

You are free to modify and extend the project for learning and demonstration purposes.

---

## ⭐ Acknowledgement

This project was developed with the help of modern web-development resources and AI-assisted development tools.

The project demonstrates how frontend technologies, browser APIs, local data storage, visualization libraries, and role-based interfaces can be combined to create a centralized college complaint management platform.

---

## ⭐ If you like this project

If you find CampusForge useful or interesting, consider giving the repository a ⭐ on GitHub.
