# 🍽️ Restaurant Reservation System

A full-stack **Restaurant Reservation System** built using the **MERN stack**. The application provides a responsive restaurant website where users can explore the restaurant, view its menu and information, and submit a reservation request by providing their personal and booking details.

The project uses **React** for the frontend and **Node.js, Express.js, and MongoDB** for handling reservations and storing booking information.

## ✨ Features

* 🏠 **Restaurant Home Page**

  * Hero section and restaurant introduction
  * Restaurant information and highlights

* 🍴 **Menu Section**

  * Displays the restaurant's menu
  * Clean and responsive presentation

* 📅 **Table Reservation**

  * Users can submit a reservation request
  * Collects:

    * First name
    * Last name
    * Email
    * Date
    * Time
    * Phone number

* ✅ **Reservation Success Page**

  * Provides confirmation after a successful reservation

* ⚠️ **Form Validation**

  * Backend validates that all required reservation fields are provided
  * Mongoose validation errors are handled and returned to the client

* 📱 **Responsive Frontend**

  * Built with React and styled for a modern restaurant website experience

* 🔗 **Frontend–Backend Integration**

  * React frontend communicates with the Express REST API
  * Reservation data is persisted in MongoDB

---

## 🛠️ Tech Stack

### Frontend

* React.js
* React Router DOM
* Axios
* React Icons
* React Scroll
* Vite
* CSS

### Backend

* Node.js
* Express.js
* MongoDB
* Mongoose
* CORS
* dotenv
* Cookie Parser
* Validator

The frontend dependencies and Vite configuration are defined in the frontend package, while the backend uses Express, Mongoose, CORS, dotenv, and related packages.

---

## 📂 Project Structure

```text
MERN_STACK_RESTAURANT_RESERVATION/
│
├── backend/
│   ├── controller/
│   │   └── reservation.js
│   │
│   ├── database/
│   │   └── dbConnection.js
│   │
│   ├── middlewares/
│   │
│   ├── models/
│   │   └── reservation.js
│   │
│   ├── routes/
│   │   └── reservationRoute.js
│   │
│   ├── app.js
│   ├── server.js
│   ├── package.json
│   └── vercel.json
│
└── frontend/
    ├── public/
    │
    ├── src/
    │   ├── Pages/
    │   │   ├── Home/
    │   │   ├── NotFound/
    │   │   └── Success/
    │   │
    │   ├── components/
    │   │   ├── About.jsx
    │   │   ├── Footer.jsx
    │   │   ├── HeroSection.jsx
    │   │   ├── Menu.jsx
    │   │   ├── Navbar.jsx
    │   │   ├── Qualities.jsx
    │   │   ├── Reservation.jsx
    │   │   ├── Team.jsx
    │   │   └── WhoAreWe.jsx
    │   │
    │   ├── App.jsx
    │   ├── main.jsx
    │   └── restApi.json
    │
    ├── package.json
    ├── vite.config.js
    └── index.html
```

The repository separates the application into `frontend` and `backend`. The frontend contains the restaurant pages and reusable components, while the backend contains controllers, routes, database connection logic, models, and middleware.

---

## 🔄 How It Works

```text
User
 │
 │  Enters reservation details
 ▼
React Frontend
 │
 │  POST request
 ▼
Express Backend
 │
 ▼
Reservation Controller
 │
 │  Validate details
 ▼
MongoDB
 │
 ▼
Reservation Stored
 │
 ▼
Success Response
 │
 ▼
Success Page
```

The reservation form sends the user's booking details to the backend through the `/api/v1/reservation/send` endpoint. The backend validates the required fields and creates a reservation document in MongoDB.

---

## 🔌 API

### Send Reservation

```http
POST /api/v1/reservation/send
```

### Request Body

```json
{
  "firstName": "John",
  "lastName": "Doe",
  "email": "john@example.com",
  "date": "2026-09-20",
  "time": "19:00",
  "phone": "9876543210"
}
```

### Successful Response

```json
{
  "success": true,
  "message": "Reservation Sent Successfully!"
}
```

The backend returns a `400` error when required reservation fields are missing and handles Mongoose validation errors through the application's error middleware.

---

## 🗄️ Database

The application uses **MongoDB** with **Mongoose**.

The database connection reads the MongoDB connection string from `MONGO_URI` and uses the `RESERVATIONS` database.

---

## ⚙️ Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/Zeeshu911/MERN_STACK_RESTAURANT_RESERVATION.git
cd MERN_STACK_RESTAURANT_RESERVATION
```

### 2. Backend Setup

```bash
cd backend
npm install
```

Create a file named:

```text
config.env
```

inside the `backend` folder.

Add:

```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
FRONTEND_URL=http://localhost:5173
```

The backend loads configuration from `config.env` and uses `FRONTEND_URL` for CORS configuration.

### 3. Start Backend

For development:

```bash
npm run dev
```

Or:

```bash
npm start
```

The backend package defines `nodemon server.js` for development and `node server.js` for production/startup.

---

### 4. Frontend Setup

Open a new terminal:

```bash
cd frontend
npm install
```

Start the development server:

```bash
npm run dev
```

---

