# Watch Store Backend

A **RESTful backend API** for the Watch Store e-commerce platform, built with **Node.js**, **Express.js**, and **MongoDB**. This backend handles **user authentication, product management, cart operations, and order processing**, including **Razorpay payment integration**.

---

## Features

- **User Authentication**
  - Signup and login using JWT
  - Password hashing for security

- **Product Management**
  - Fetch products by category, gender, and type
  - Supports filtering and detailed product information

- **Cart Management**
  - Add, update, and remove products in the cart
  - Cart associated with authenticated users

- **Order Management**
  - Place orders with multiple products
  - Calculate total price
  - Razorpay integration for online payment
  - Payment verification

- **Middleware**
  - JWT authentication for secure routes
  - Centralized error handling

---

## Tech Stack

- **Backend:** Node.js, Express.js  
- **Database:** MongoDB, Mongoose  
- **Authentication:** JWT  
- **Payment Gateway:** Razorpay  
- **Others:** bcrypt, dotenv, CORS  

---

## Installation

1. Clone the repository:
2. Create a .env file and add the following variables:
MONGO_URI=<Your MongoDB Connection String>
JWT_SECRET=<Your JWT Secret Key>
RAZORPAY_KEY_ID=<Your Razorpay Key ID>
RAZORPAY_KEY_SECRET=<Your Razorpay Secret Key>
PORT=5000
```bash
git clone https://github.com/prajapativikrant/EcomerceBackend.git
cd EcomerceBackend
npm install

Create a .env file and add the following variables:
MONGO_URI=<Your MongoDB Connection String>
JWT_SECRET=<Your JWT Secret Key>
RAZORPAY_KEY_ID=<Your Razorpay Key ID>
RAZORPAY_KEY_SECRET=<Your Razorpay Secret Key>
PORT=5000
npm run dev

```
##API Endpoints

1. Auth Routes <br>
| Method | Endpoint         | Description         | Protected | <br>
| ------ | ---------------- | ------------------- | --------- | <br>
| POST   | /api/auth/signup | Register a new user | ❌         | <br>
| POST   | /api/auth/login  | Login and get JWT   | ❌         | <br>
| GET    | /api/auth/       | Get user details    | ✅         | <br>

2. Product Routes <br>
| Method | Endpoint                                        | Description                  | Protected | <br>
| ------ | ----------------------------------------------- | ---------------------------- | --------- | <br>
| GET    | /api/products/category                          | Get all product categories   | ❌         | <br>
| GET    | /api/products/:gender                           | Get products by gender       | ❌         | <br>
| GET    | /api/products/:gender/:watchCategory            | Get watches by category      | ❌         | <br>
| GET    | /api/products/:gender/:watchCategory/:name/:url | Get specific product details | ❌         | <br>

3. Cart Routes<br>
| Method | Endpoint      | Description              | Protected | <br>
| ------ | ------------- | ------------------------ | --------- | <br>
| GET    | /api/cart/    | Get user cart            | ✅         |<br>
| POST   | /api/cart/    | Add product to cart      | ✅         |<br>
| PUT    | /api/cart/:id | Update product quantity  | ✅         |<br>
| DELETE | /api/cart/:id | Remove product from cart | ✅         |<br>

4. Order Routes<br>
| Method | Endpoint          | Description             | Protected |<br>
| ------ | ----------------- | ----------------------- | --------- |<br>
| POST   | /api/order/       | Place a new order       | ✅         |<br>
| POST   | /api/order/order  | Create Razorpay order   | ❌         |<br>
| POST   | /api/order/verify | Verify Razorpay payment | ❌         |<br>










