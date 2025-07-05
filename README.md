## 🎟️ Project Title: _"Eventify Lite"_ – Basic Event Booking API

### 🧠 Summary

Students will build a **basic event booking system** API where users can register, login, create events, and book seats (no real-time concurrency or payment required). Focus is on **Node.js fundamentals**, **Express**, **CRUD**, **authentication (JWT)**, and **basic database use (SQLite or MongoDB)**.

---

## 🧱 Core Features

### 1. **Authentication**

- `POST /auth/register` – Register with `name`, `email`, `password`
- `POST /auth/login` – Login with `email` & `password`, receive a JWT token

### 2. **Events**

- `GET /events` – List all events
- `GET /events/:id` – Get one event by ID
- `POST /events` – (Authenticated) Create new event with:

  ```json
  {
    "title": "ASAKE Live",
    "date": "2025-08-01",
    "location": "Eko Hotel",
    "availableSeats": 100
  }
  ```

- `PUT /events/:id` – (Authenticated) Edit an event
- `DELETE /events/:id` – (Authenticated) Delete an event

### 3. **Booking**

- `POST /events/:id/book` – Book 1 or more seats from an event
  Payload: `{ "seats": 2 }`
  Reduces `availableSeats` on successful booking.

### 4. **My Bookings**

- `GET /my-bookings` – List events booked by the logged-in user

---

## 💾 Database Schema Example

**Users**

- id
- name
- email
- password (hashed)

**Events**

- id
- title
- date
- location
- availableSeats

**Bookings**

- id
- userId
- eventId
- seats

---

## 🔐 Authentication

- Use **JWT tokens** for protected routes
- Middleware: `authenticateToken` to guard `POST /events`, `POST /book`, etc.

---

## 🛠️ Technologies to Use

- Node.js
- Express.js
- MongoDB or SQLite (with Mongoose or Sequelize)
- bcrypt for password hashing
- jsonwebtoken for auth
- Postman for testing

---

## 📄 What to Submit

1. Source code (GitHub repo)
2. Postman collection (with sample requests)
3. README.md with:

   - Setup instructions
   - API documentation

4. Export your database and add to your repo
