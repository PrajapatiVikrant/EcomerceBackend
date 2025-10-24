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

1. Auth Routes
| Method | Endpoint         | Description         | Protected |
| ------ | ---------------- | ------------------- | --------- |
| POST   | /api/auth/signup | Register a new user | ❌         |
| POST   | /api/auth/login  | Login and get JWT   | ❌         |
| GET    | /api/auth/       | Get user details    | ✅         |

2. Product Routes
| Method | Endpoint                                        | Description                  | Protected |
| ------ | ----------------------------------------------- | ---------------------------- | --------- |
| GET    | /api/products/category                          | Get all product categories   | ❌         |
| GET    | /api/products/:gender                           | Get products by gender       | ❌         |
| GET    | /api/products/:gender/:watchCategory            | Get watches by category      | ❌         |
| GET    | /api/products/:gender/:watchCategory/:name/:url | Get specific product details | ❌         |

3. Cart Routes
| Method | Endpoint      | Description              | Protected |
| ------ | ------------- | ------------------------ | --------- |
| GET    | /api/cart/    | Get user cart            | ✅         |
| POST   | /api/cart/    | Add product to cart      | ✅         |
| PUT    | /api/cart/:id | Update product quantity  | ✅         |
| DELETE | /api/cart/:id | Remove product from cart | ✅         |

4. Order Routes
| Method | Endpoint          | Description             | Protected |
| ------ | ----------------- | ----------------------- | --------- |
| POST   | /api/order/       | Place a new order       | ✅         |
| POST   | /api/order/order  | Create Razorpay order   | ❌         |
| POST   | /api/order/verify | Verify Razorpay payment | ❌         |










