# 🩺 Appointy — Doctor Appointment Web App

**Appointy** is a full-stack doctor appointment platform designed to simplify healthcare appointment management for **patients, doctors, and administrators**.

The application provides role-based authentication, doctor discovery, appointment scheduling, profile management, administrative controls, and online payment integration using the **MERN stack**.

---

## ✨ Features

### 👤 Patient Portal

* Patient registration and secure login
* Browse and search doctors by specialty
* View detailed doctor profiles
* Book doctor appointments
* Select appointment date and time
* Multiple payment methods:

  * Cash
  * Stripe
  * Razorpay
* View upcoming and previous appointments
* Cancel or reschedule appointments
* Manage personal profile
* Upload and update profile picture
* Update:

  * Name
  * Email
  * Address
  * Gender
  * Date of birth

---

### 🩺 Doctor Portal

Doctors have access to a dedicated dashboard where they can:

* View upcoming appointments
* View patient information
* Track appointment status
* View total earnings
* View total patients
* View total appointments
* Mark appointments as completed
* Cancel appointments
* Manage doctor profile
* Update:

  * Description
  * Consultation fees
  * Address
  * Availability status

---

### 🛠️ Admin Portal

Administrators can manage the entire platform through a centralized dashboard.

#### Dashboard

* Total doctors
* Total patients
* Total appointments
* Recent bookings
* Appointment management

#### Doctor Management

* Add new doctors
* View registered doctors
* Edit doctor information
* Delete doctor profiles

Doctor information includes:

* Profile image
* Name
* Specialty
* Email
* Password
* Degree
* Experience
* Address
* Consultation fees
* Description

#### Appointment Management

* View all appointments
* View patient information
* View doctor information
* Cancel appointments
* Mark appointments as completed

---

## 🏠 Pages & User Experience

### Home Page

The homepage provides quick access to the platform's main functionality.

Users can:

* Search for doctors
* Browse doctors by specialty
* View top doctors
* Open doctor profiles
* Navigate to About, Contact, Privacy Policy, and Delivery Information pages

---

### 🩺 All Doctors

Displays all available doctors with specialty-based filtering.

Users can select a doctor to view their profile and proceed to the appointment booking page.

---

### 📄 About Us

Provides information about Appointy's vision and mission.

#### Why Choose Appointy?

* **Efficiency** — Streamlined appointment scheduling
* **Convenience** — Online booking and payment
* **Personalization** — User-focused healthcare experience

---

### 📞 Contact Us

Provides:

* Office address
* Contact information
* Job opportunities section
* Navigation links to other pages

---

### 📅 Doctor Appointment

The appointment page displays detailed information about a selected doctor, including:

* Profile picture
* Qualifications
* Experience
* Description
* Consultation fees
* Availability

Patients can select:

* Appointment date
* Appointment time
* Payment method

Users must be authenticated before booking an appointment.

---

### 👤 User Profile

Authenticated patients can:

* View and edit their profile
* Upload a profile picture
* Update personal information
* View upcoming appointments
* View previous appointments
* Log out

---

## 💳 Payment Integration

Appointy supports multiple payment methods:

* 💵 Cash Payment
* 💳 Stripe
* 💳 Razorpay

Payment processing is integrated into the appointment booking workflow to provide a smooth checkout experience.

---

## 🛠️ Tech Stack

| Technology     | Purpose            |
| -------------- | ------------------ |
| **React.js**   | Frontend           |
| **Node.js**    | Backend runtime    |
| **Express.js** | REST API & server  |
| **MongoDB**    | Database           |
| **JWT**        | Authentication     |
| **Stripe**     | Payment processing |
| **Razorpay**   | Payment processing |

### Architecture

**Frontend → REST API → Express/Node.js → MongoDB**

Authentication and authorization are handled using **JSON Web Tokens (JWT)**.

---

## 🔐 Authentication & Authorization

Appointy uses role-based authentication with three user types:

```text
Patient
   ↓
Book & Manage Appointments

Doctor
   ↓
Manage Appointments & Profile

Admin
   ↓
Manage Doctors, Patients & Appointments
```

JWT authentication is used to protect authenticated routes and restrict access based on user roles.

---

## 📁 Project Structure

```text
appointy/
│
├── client/                 # React frontend
│   ├── src/
│   ├── public/
│   └── package.json
│
├── server/                 # Node.js + Express backend
│   ├── config/             # Database & service configuration
│   ├── controllers/        # Business logic
│   ├── middleware/         # Authentication & error handling
│   ├── models/             # MongoDB schemas
│   ├── routes/             # API routes
│   ├── utils/              # Utility functions
│   └── server.js           # Backend entry point
│
├── .env                    # Environment variables
├── package.json
└── README.md
```

> **Note:** Keep sensitive credentials such as database URLs, JWT secrets, and payment API keys inside `.env`. Never commit your `.env` file to GitHub.

---

## ⚙️ Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/appointy.git
cd appointy
```

### 2. Install Backend Dependencies

```bash
npm install
```

### 3. Install Frontend Dependencies

```bash
cd client
npm install
cd ..
```

---

## 🔑 Environment Configuration

Create a `.env` file in the **root directory**:

```env
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret

STRIPE_API_KEY=your_stripe_api_key

RAZORPAY_KEY_ID=your_razorpay_key_id
RAZORPAY_KEY_SECRET=your_razorpay_key_secret
```

### Recommended `.gitignore`

Make sure your `.gitignore` includes:

```gitignore
node_modules/
.env
dist/
build/
```

**Never push real API keys, database credentials, or JWT secrets to GitHub.**

---

## ▶️ Running the Application

From the project root:

```bash
npm run dev
```

If the frontend and backend are configured to run separately, start them independently:

### Backend

```bash
npm run dev
```

### Frontend

```bash
cd client
npm run dev
```

The application will then be available through the local development URLs shown in your terminal.

---

## 🔄 Application Flow

```text
                ┌───────────────┐
                │    Appointy   │
                └───────┬───────┘
                        │
          ┌─────────────┼─────────────┐
          │             │             │
       Patient        Doctor         Admin
          │             │             │
          ▼             ▼             ▼
      Browse &       Manage        Manage
       Book          Schedule      Platform
          │             │             │
          └─────────────┼─────────────┘
                        │
                        ▼
                 Express / Node.js
                        │
                        ▼
                    MongoDB
```

---

## 🔒 Security

The application uses:

* JWT-based authentication
* Role-based authorization
* Protected API routes
* Environment variables for sensitive configuration
* Secure payment gateway integration

---

## 🚀 Future Improvements

Potential improvements include:

* Email appointment notifications
* Doctor reviews and ratings
* Automated appointment reminders
* Google Calendar integration
* Real-time notifications
* Advanced admin analytics
* Prescription management
* Medical document uploads
* Video consultation support
* Improved payment verification

---

## 🤝 Contributing

Contributions are welcome!

To contribute:

```bash
# Fork the repository

# Create a feature branch
git checkout -b feature/your-feature

# Commit your changes
git commit -m "Add your feature"

# Push the branch
git push origin feature/your-feature
```

Then open a **Pull Request**.

---

## 📜 License

This project is available for educational and development purposes.

---

## 🙌 Acknowledgements

Special thanks to the developers and communities behind:

* MongoDB
* Express.js
* React.js
* Node.js
* Stripe
* Razorpay

for providing the technologies and services used to build Appointy.
