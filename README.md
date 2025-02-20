# Property-Booking-API
###**Final README.md for Submission**
```markdown
# Property Booking API

## 🏠 Overview
This is a **Node.js REST API** for managing **properties and bookings** in a real estate platform. It allows users to:
- **Add properties**
- **Retrieve available properties**
- **Book a property**
- **Confirm a booking (simulate payment processing)**

---

## 🚀 Features
- **Add a new property** (`POST /api/properties`)
- **Get all available properties** (`GET /api/properties`)
- **Book a property** (`POST /api/bookings/bookProperty`)
- **Confirm a booking** (`PUT /api/bookings/confirmBooking/:bookingId`)

---

## 🛠️ Setup & Installation
### **1️⃣ Install Dependencies**
```sh
npm install
```

### **2️⃣ Set Up Environment Variables**
Create a `.env` file in the root directory and add:
```
MONGO_URI=mongodb+srv://<username>:<password>@cluster0.mongodb.net/propertyBookingDB?retryWrites=true&w=majority
PORT=5000
```
> **Note:** Replace `<username>` and `<password>` with your actual MongoDB Atlas credentials.

### **3️⃣ Start the Server**
```sh
node server.js
```
or (for development with auto-reload)
```sh
npx nodemon server.js
```
The API will now run on **`http://localhost:5000`**.

---

## 📝 API Endpoints

### **1️⃣ Properties**
#### **Create Property**
- **Endpoint:** `POST /api/properties`
- **Request Body (JSON):**
  ```json
  {
    "name": "Luxury Apartment",
    "location": "Mumbai",
    "price": 5000000,
    "availableUnits": 3
  }
  ```
- **Response:** `201 Created`
  ```json
  {
    "_id": "654c1234a1b2c3d4e5f6g7h8",
    "name": "Luxury Apartment",
    "location": "Mumbai",
    "price": 5000000,
    "availableUnits": 3
  }
  ```

#### **Get All Available Properties**
- **Endpoint:** `GET /api/properties`
- **Response:** `200 OK`
  ```json
  [
    {
      "_id": "654c1234a1b2c3d4e5f6g7h8",
      "name": "Luxury Apartment",
      "location": "Mumbai",
      "price": 5000000,
      "availableUnits": 3
    }
  ]
  ```

---

### **2️⃣ Bookings**
#### **Book a Property**
- **Endpoint:** `POST /api/bookings/bookProperty`
- **Request Body (JSON):**
  ```json
  {
    "userId": "user123",
    "propertyId": "654c1234a1b2c3d4e5f6g7h8",
    "bookingDate": "2025-02-20"
  }
  ```
- **Response:** `201 Created`
  ```json
  {
    "_id": "65b7a1d6a1e69d1f8a123456",
    "userId": "user123",
    "propertyId": "654c1234a1b2c3d4e5f6g7h8",
    "status": "pending",
    "bookingDate": "2025-02-20"
  }
  ```

#### **Confirm a Booking (Simulated Payment)**
- **Endpoint:** `PUT /api/bookings/confirmBooking/:bookingId`
- **Response:** `200 OK`
  ```json
  {
    "message": "Booking confirmed",
    "booking": {
      "_id": "65b7a1d6a1e69d1f8a123456",
      "userId": "user123",
      "propertyId": "654c1234a1b2c3d4e5f6g7h8",
      "status": "confirmed",
      "bookingDate": "2025-02-20"
    }
  }
  ```

---

## 🛠️ Running Tests
### **Run API Tests**
To test the API using Jest and Supertest:
```sh
npm test
```
> **Note:** This runs a basic test case for creating and retrieving properties.

---

## 🎯 Next Steps (Future Improvements)
- **Add authentication using JWT**
- **Deploy the API on a cloud platform (Render, Railway, AWS, etc.)**
- **Implement a frontend UI (React or Next.js)**
- **Improve error handling and validation**

---

### 🎉 **Final Review**
✅ **Code is well-structured (`models/`, `routes/`, `controllers/`, `config/`)**  
✅ **README.md includes setup instructions and API documentation**  
✅ **Basic Jest & Supertest API tests are implemented and passing (`npm test`)**  
✅ **MongoDB connection is properly configured**  

You’re now fully ready to submit! 🚀🔥 Let me know if you need any last-minute refinements. 😃
