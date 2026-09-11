#LIVE DEMO:-https://multi-tenant-ecommerce-live.vercel.app/

## 1. Project Overview

### Project Title
**Multi-Tenant E-Commerce Platform**

### Project Description
The Multi-Tenant E-Commerce Platform is a web-based application designed to allow multiple vendors to manage their online stores within a single centralized system. The platform supports three major user roles:

- Super Admin
- Vendor
- Customer

Each vendor can manage products, inventory, orders, and customers independently while the Super Admin monitors overall platform activities. Customers can browse products, add items to cart, place orders, and manage their accounts.

The system is developed using the MERN Stack (MongoDB, Express.js, React.js, Node.js) and follows a scalable architecture suitable for SaaS-based e-commerce solutions.

---

# 2. Problem Statement

Small and medium businesses often face difficulties in creating and maintaining their own e-commerce websites because of high development and maintenance costs.

This project solves this problem by providing a shared platform where multiple vendors can create and manage their stores without building separate systems.

---

# 3. Objectives

- Provide a centralized e-commerce platform for multiple vendors.
- Allow vendors to manage products and orders independently.
- Enable customers to purchase products easily.
- Ensure secure authentication and authorization.
- Maintain tenant data isolation.
- Provide an admin dashboard for monitoring platform activities.
- Support scalable architecture for future growth.

---

# 4. Scope

### In Scope

- User Registration & Login
- Role-Based Access Control
- Product Management
- Cart Management
- Order Management
- Payment Processing
- Password Recovery
- Vendor Dashboard
- Admin Dashboard
- Customer Dashboard

### Out of Scope

- Mobile Application
- AI Recommendation Engine
- Multi-language Support
- Advanced Analytics
- Subscription Billing

---

# 5. Technology Stack

## Frontend

- React.js
- React Router DOM
- Tailwind CSS
- Axios
- Vite

## Backend

- Node.js
- Express.js

## Database

- MongoDB
- Mongoose

## Security

- JWT Authentication
- Bcrypt.js Password Hashing
- Helmet.js

## Other Services

- Nodemailer
- Cloudinary (Optional)
- Stripe/Payment Gateway Integration

---

# 6. System Architecture

```
Customer/Vendor/Admin
          |
          V
      React Frontend
          |
          V
      Express API
          |
          V
    Business Logic
          |
          V
       MongoDB
```

---

# 7. User Roles

## 7.1 Super Admin

### Responsibilities

- Manage vendors
- Monitor platform activities
- View platform statistics
- Manage payouts
- Manage announcements

### Permissions

- View all vendors
- Approve/Block vendors
- View revenue reports
- Manage platform settings

---

## 7.2 Vendor

### Responsibilities

- Manage products
- Manage inventory
- Manage orders
- View sales data

### Permissions

- Add Product
- Update Product
- Delete Product
- Manage Orders

---

## 7.3 Customer

### Responsibilities

- Browse products
- Add items to cart
- Place orders
- Manage profile

### Permissions

- View Products
- Create Orders
- Manage Cart
- View Order History

---

# 8. Functional Requirements

## FR-1 User Registration

### Description
Users should be able to register as customers or vendors.

### Input

- Name
- Email
- Password

### Output

- Account created successfully

---

## FR-2 User Login

### Description
Registered users should be able to login.

### Input

- Email-anuj@gmail.com
- Password-123456

### Output

- JWT Token
- User Information

---

## FR-3 Forgot Password

### Description
Users can reset forgotten passwords.

### Process

1. Enter email
2. Receive reset link
3. Create new password

---

## FR-4 Product Management

### Description
Vendors can manage products.

### Features

- Add Product
- Edit Product
- Delete Product
- View Product

### Product Details

- Product Name
- Description
- Price
- Category
- Image
- Stock

---

## FR-5 Product Browsing

### Description
Customers can browse available products.

### Features

- View Products
- View Product Details
- Search Products

---

## FR-6 Cart Management

### Description
Customers can manage shopping carts.

### Features

- Add Item
- Remove Item
- Update Quantity
- Calculate Total Price

---

## FR-7 Order Management

### Description
Customers can place orders and vendors can manage them.

### Features

- Create Order
- View Orders
- Update Order Status
- Cancel Order

---

## FR-8 Payment Management

### Description
The system processes online payments.

### Features

- Payment Verification
- Coupon Validation
- Checkout Session

---

## FR-9 Admin Dashboard

### Description
Admin can monitor platform activities.

### Features

- Revenue Reports
- Vendor Management
- Activity Logs
- Platform Statistics

---

# 9. Non-Functional Requirements

## Performance

- API response time less than 3 seconds.
- Support multiple concurrent users.

## Security

- Password encryption using Bcrypt.
- JWT authentication.
- Role-based authorization.
- Secure API endpoints.

## Scalability

- Modular backend architecture.
- Easy integration of microservices in future.

## Reliability

- 99% uptime target.
- Proper error handling.

## Usability

- User-friendly interface.
- Responsive design.

---

# 10. Database Design

## User Collection

| Field | Type |
|---------|---------|
| _id | ObjectId |
| name | String |
| email | String |
| password | String |
| role | String |
| createdAt | Date |

---

## Product Collection

| Field | Type |
|---------|---------|
| _id | ObjectId |
| name | String |
| description | String |
| price | Number |
| stock | Number |
| image | String |
| vendorId | ObjectId |

---

## Cart Collection

| Field | Type |
|---------|---------|
| _id | ObjectId |
| userId | ObjectId |
| items | Array |
| totalPrice | Number |

---

## Order Collection

| Field | Type |
|---------|---------|
| _id | ObjectId |
| userId | ObjectId |
| products | Array |
| totalAmount | Number |
| status | String |

---

# 11. API Endpoints

## Authentication

| Method | Endpoint |
|----------|------------|
| POST | /api/auth/signup |
| POST | /api/auth/login |
| POST | /api/auth/forgot-password |
| POST | /api/auth/reset-password |

---

## Products

| Method | Endpoint |
|----------|------------|
| GET | /api/products |
| GET | /api/products/detail/:id |
| POST | /api/products/add |
| PUT | /api/products/:id |
| DELETE | /api/products/:id |

---

## Cart

| Method | Endpoint |
|----------|------------|
| POST | /api/cart/add |
| GET | /api/cart/:userId |
| DELETE | /api/cart/remove |

---

## Orders

| Method | Endpoint |
|----------|------------|
| POST | /api/orders/place |
| GET | /api/orders/user/:userId |
| PUT | /api/orders/:id |

---

## Payments

| Method | Endpoint |
|----------|------------|
| POST | /api/payments/create-checkout-session |
| POST | /api/payments/verify-payment |
| GET | /api/payments/coupons |

---

# 12. Security Requirements

- Password Hashing using Bcrypt
- JWT Token Authentication
- Protected Routes
- Role-Based Access Control
- Secure Environment Variables
- Input Validation
- API Error Handling

---

# 13. Testing Strategy

## Unit Testing

- Authentication
- Product Management
- Cart Operations
- Order Operations

## Integration Testing

- API Endpoints
- Database Connectivity

## User Acceptance Testing

- Customer Workflow
- Vendor Workflow
- Admin Workflow

---

# 14. Future Enhancements

- Microservices Architecture
- AI Product Recommendation
- Multi-language Support
- Mobile Application
- Real Payment Gateway Integration
- Inventory Analytics Dashboard
- Vendor Subscription Plans
- Chat Support System

---

# 15. Expected Outcomes

- Centralized Multi-Vendor Platform
- Improved Vendor Management
- Better Customer Shopping Experience
- Secure Transactions
- Scalable SaaS Infrastructure

---

# 16. Team Information

### Project Name
Multi-Tenant E-Commerce Platform

### Domain
Web Development

### Technology
MERN Stack

### Developed By
Anuj Bhaskar- Worked in week 1
Gaurav Vishwakarma- worked in week 2 (team leader)
Riya Mishra- worked in week 3
Srivalli Kanna- worked in week 4

### Duration
4 Weeks Internship Project

---

# License

This project is developed for educational and internship purposes.

© 2026 Multi-Tenant E-Commerce Platform
