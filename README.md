# Online Blood Donation System

A complete database-driven web application that connects blood donors with hospitals in need. Designed as a DBMS course project at FAST-NUCES Karachi, the system includes user role management, secure login, real-time appointment scheduling, donor-hospital matchmaking, and an administrative dashboard.

--- 

## Overview

The **Online Blood Donation System** simplifies and streamlines the blood donation process. Built using Python and Flask, it features three user roles:

- **Admin**
- **Donor**
- **Hospital**

Each user type has specific dashboards and functionality. The backend logic is implemented in `app.py`, and all interactions persist in a normalized SQL database.

---

## Key Features

### Authentication
- Role-based registration and login system
- Templates: `register.html`, `login.html`

### Donor Module
- Update and manage personal profiles (`donor_profile.html`)
- Search hospitals by blood type or location (`search.html`)
- Schedule appointments

### Hospital Module
- Access hospital dashboard (`hospital_dashboard.html`)
- View, confirm, or cancel donor appointments
- Update hospital details

### Appointment Management
- Donors can book or cancel appointments
- Hospitals manage appointment requests

### Donor-Hospital Matching
- Matches based on:
  - **Blood type compatibility**
  - **City/location proximity**

### Admin Panel
- Admin login via `admin_login.html`
- Admin dashboard: manage users, hospitals, and blood data (`admin_dashboard.html`)
- In-built chat system for donor support (timestamps included)
- Login activity logging via `login_logs.log`

---

## Project Structure

```plaintext
Online-Blood-Donation-System/
│
├── app.py                   # Flask backend controller
├── login_logs.log           # System-generated user login logs
├── DB PROJECT REPORT        # Summary of the whole project
├── README.md                # How to use
│
├── sql/
│   └── bd (1).sql           # MySQL database dump file
│
├── templates/               # HTML UI pages
│   ├── index.html
│   ├── register.html
│   ├── login.html
│   ├── donor_profile.html
│   ├── update_user.html
│   ├── search.html
│   ├── hospital_dashboard.html
│   ├── admin_dashboard.html
│   └── admin_login.html
│
├── static/                  # Static assets
│   ├── *.jpg, *.png         # Images for branding and blood awareness
│   └── Plans.ttf            # Custom font used in UI
│
└── .git/                    # Git metadata (if repository cloned)
```

---

## Tech Stack

Backend: Python (Flask)\
Frontend: HTML5, CSS3\
Database: MySQL\
Web Server: Localhost (XAMPP / WAMP)\
Versioning: Git & GitHub

---

## Database

### SQL Dump File

- File: `sql/bd (1).sql`
- Includes schema and test data for donors, hospitals, appointments, and user accounts.

### ERD & Normalization

- The system uses **3NF-normalized** design.
- Proper relational modeling for:
  - Donors ↔ Hospitals ↔ Appointments
  - Admin-managed lookup and reference tables

---

## How to Run Locally

1. **Clone the repository**
   ```bash
   git clone https://github.com/Abdul-Wasey25/Online-Blood-Donation-System-bd.git
   cd Online-Blood-Donation-System

2. **Install Dependencies**
    ```bash
    pip install flask mysql-connector-python

3. **Configure database in `app.py`**
    ```bash
    # Replace with your local MySQL credentials
    db = mysql.connector.connect(
        host="localhost",
        user="your_username",
        password="your_password",
        database="blood_donation_db"
    )

4. **Import the SQL dump**
    - Open phpMyAdmin through XAMPP
    - Create a new database (e.g., blood_donation_db)
    - Import `sql/bd (1).sql`

5. **Run the application**
    ```bash
    python app.py

6. **Open in browser**\
Navigate to: http://localhost:5000
