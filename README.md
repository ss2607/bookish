

# 📚 Bookish — Online Book Marketplace

Bookish is a full-stack web platform for buying, selling, and managing books online. It provides separate experiences for **buyers, sellers, and administrators**, with role-based dashboards and features for browsing books, shopping, payments, subscriptions, personal libraries, reviews, complaints, inventory management, and platform administration.

Built using **React, Node.js, Express.js, MongoDB, and modern web technologies**.

---

## 📺 Demo Video

**Demo video (Unlisted):** `(https://youtu.be/u79hp5E6ZAY)`

> The application is deployed with a React frontend and Node.js backend.

---

## ✨ Features

### 🛒 Buyer

- Browse and search available books
- View detailed book information
- Add books to cart
- Purchase books online
- Subscription-based plans
- Personal digital library
- Track reading progress
- Highlight and bookmark content
- Watch video reviews
- Submit and track complaints
- Manage profile and addresses
- View order history

### 🏪 Seller

- Upload books with details and images
- Manage listed books
- Manage inventory
- Track orders
- View sales analytics
- Manage book reviews and videos
- Track commissions

### 🛡️ Admin

- Manage users and roles
- Approve or reject book listings
- Moderate platform content
- View platform reports
- Monitor users, books, orders, and complaints
- Resolve customer complaints
- View platform-wide analytics

---

## 🛠️ Tech Stack

### Frontend

- **React 18.2** — UI development
- **Vite** — Build tool and development server
- **Redux Toolkit** — State management
- **Redux Persist** — Persistent application state
- **React Router DOM** — Client-side routing
- **Tailwind CSS** — Styling
- **Axios** — API communication
- **React Hook Form** — Form handling
- **Zod** — Form validation
- **Stripe** — Payment integration
- **React PDF** — PDF rendering
- **Recharts** — Data visualization
- **Framer Motion** — Animations
- **Lucide React** — Icons

### Backend

- **Node.js** — Runtime environment
- **Express.js** — Backend framework
- **MongoDB** — Database
- **Mongoose** — MongoDB ODM
- **Passport.js** — Authentication
- **Cloudinary** — Image and file storage
- **Stripe** — Payment processing
- **Node-cron** — Scheduled tasks

### Backend Middleware & Security

- **Multer** — File uploads
- **Morgan** — HTTP request logging
- **CORS** — Cross-origin resource sharing
- **Express Session** — Session management
- **Connect Mongo** — MongoDB session store
- **Helmet** — Security headers
- **Express Rate Limit** — Rate limiting
- **bcryptjs** — Password hashing
- **Connect Flash** — Flash messages
- **Method Override** — HTTP method handling

---

## 🏗️ Architecture

Bookish follows a full-stack architecture consisting of:

```text
React Frontend
      │
      │ REST API
      ▼
Node.js + Express Backend
      │
      ├── Authentication
      ├── Buyer Services
      ├── Seller Services
      ├── Admin Services
      ├── Order Management
      └── Subscription Management
      │
      ▼
MongoDB Database

External Services:
├── Stripe       → Payments & subscriptions
└── Cloudinary   → Images & file storage
```

---

## 📁 Project Structure

```text
bookish/
│
├── backend/
│   ├── app.js
│   ├── package.json
│   │
│   ├── config/
│   │   ├── cloudinary.js
│   │   ├── db.js
│   │   ├── passport.js
│   │   └── subscriptionCron.js
│   │
│   ├── controllers/
│   │   ├── adminController.js
│   │   ├── authController.js
│   │   ├── buyerController.js
│   │   ├── orderController.js
│   │   ├── sellerController.js
│   │   └── subscriptionController.js
│   │
│   ├── models/
│   │   ├── User.js
│   │   ├── Book.js
│   │   ├── Order.js
│   │   ├── Cart.js
│   │   ├── Complaint.js
│   │   ├── Library.js
│   │   └── Subscription.js
│   │
│   ├── routes/
│   │   ├── auth.js
│   │   ├── books.js
│   │   ├── buyer.js
│   │   ├── seller.js
│   │   ├── admin.js
│   │   └── orders.js
│   │
│   ├── middleware/
│   │   └── auth.js
│   │
│   └── uploads/
│
├── frontend/
│   ├── package.json
│   ├── vite.config.js
│   ├── tailwind.config.js
│   ├── index.html
│   │
│   ├── src/
│   │   ├── main.jsx
│   │   ├── App.jsx
│   │   ├── components/
│   │   ├── pages/
│   │   ├── redux/
│   │   ├── services/
│   │   ├── context/
│   │   ├── utils/
│   │   ├── schemas/
│   │   └── styles/
│   │
│   └── public/
│
└── README.md
```

---

## 🔐 Authentication & Authorization

Bookish implements role-based access control with separate functionality for:

- **Buyer**
- **Seller**
- **Admin**

Protected routes and backend authentication ensure that users can only access functionality permitted for their role.

Authentication uses **Passport.js**, sessions, MongoDB session storage, and password hashing with **bcryptjs**.

---

## 💳 Payments & Subscriptions

Bookish integrates **Stripe** for payment processing.

Supported functionality includes:

- One-time book purchases
- Subscription plans
- Recurring subscriptions
- Secure payment processing
- Subscription renewal using scheduled backend tasks

Stripe credentials are stored using environment variables and are not included in the source code.

---

## ☁️ File & Image Management

Bookish uses **Cloudinary** for storing and managing uploaded images and files.

The backend uses **Multer** to handle multipart file uploads before transferring files to cloud storage.

---

## 🔌 API Structure

The backend exposes REST-style API routes organized by functionality:

```text
/api/auth/*            → Authentication
/api/books/*           → Book management
/api/buyer/*           → Buyer operations
/api/seller/*          → Seller operations
/api/admin/*           → Admin operations
/api/orders/*          → Order management
/api/subscription/*    → Subscription management
```

---

## 🔑 Key Implementation Details

### Frontend

- Redux Toolkit for centralized state management
- Redux Persist for state persistence
- React Router for protected and role-based navigation
- Axios services for API communication
- React Hook Form and Zod for form validation
- Tailwind CSS for responsive UI
- Framer Motion for animations

### Backend

- Express.js REST API
- Passport.js authentication
- MongoDB with Mongoose
- Session-based authentication
- Cloudinary file storage
- Stripe payment integration
- Scheduled subscription tasks with Node-cron
- Helmet security middleware
- Rate limiting
- CORS configuration
- Morgan request logging

---

## 📦 Prerequisites

Before running the project locally, make sure you have:

- Node.js 14+
- npm
- MongoDB (local installation or MongoDB Atlas)
- Git
- Cloudinary account
- Stripe account

---

## 🚀 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/ss2607/bookish.git
cd bookish
```

---

### 2. Setup Backend

```bash
cd backend
npm install
```

Create a `.env` file inside the `backend` directory.

Example:

```env
MONGODB_URI=mongodb+srv://<user>:<password>@cluster0.mongodb.net/bookishdb

CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret

STRIPE_SECRET_KEY=your_stripe_secret_key
STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key

SESSION_SECRET=your_session_secret

PORT=4000
NODE_ENV=development

FRONTEND_URL=http://localhost:5173
```

Start the backend:

```bash
npm run dev
```

Or:

```bash
npm start
```

The backend will run on:

```text
http://localhost:4000
```

---

### 3. Setup Frontend

Open another terminal:

```bash
cd frontend
npm install
```

Create a `.env` file inside the `frontend` directory:

```env
VITE_API_URL=http://localhost:4000/api
VITE_STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key
```

Start the frontend:

```bash
npm run dev
```

The frontend will run on:

```text
http://localhost:5173
```

---

## 🏗️ Production Build

### Frontend

```bash
cd frontend
npm run build
```

To preview the production build:

```bash
npm run preview
```

The production build will be generated inside:

```text
frontend/dist/
```

### Backend

```bash
cd backend
npm start
```

---

## 🔒 Environment Variables

Sensitive credentials should **never be committed to GitHub**.

The following types of values should be stored in `.env` files:

- MongoDB connection string
- Cloudinary credentials
- Stripe secret key
- Stripe publishable key
- Session secret
- API URLs

Make sure `.env` files are included in `.gitignore`.

Example:

```text
.env
.env.local
.env.production
```

---

## 🧪 Testing & Development

Important application flows include:

- User authentication
- Role-based navigation
- Book browsing and search
- Cart operations
- Book purchases
- Subscription handling
- Personal library
- Seller book uploads
- Inventory management
- Order management
- Admin book moderation
- Complaint submission and resolution
- Form validation
- API communication

Browser developer tools can be used to inspect API requests and application state during development.

---

## 📊 Current Status

**Version:** 1.0

**Status:** Deployed and functional

The core buyer, seller, and admin workflows are implemented, along with payment, subscription, authentication, file upload, and database functionality.

---

## 🐞 Troubleshooting

### Backend not starting

- Check that MongoDB is reachable.
- Verify the backend `.env` variables.
- Run `npm install` inside `backend`.
- Check whether port `4000` is already in use.

### Frontend not loading data

- Verify that the backend is running.
- Check `VITE_API_URL`.
- Check the browser console for errors.
- Verify CORS configuration.

### CORS errors

Make sure the backend `FRONTEND_URL` matches the frontend URL.

For local development:

```env
FRONTEND_URL=http://localhost:5173
```

### File upload problems

- Verify Cloudinary credentials.
- Check Multer configuration.
- Make sure the required upload directories exist.

### Payment problems

- Verify Stripe environment variables.
- Use valid Stripe test credentials when developing locally.
- Check the browser console and backend logs for API errors.

---

## 👩‍💻 Author

**Shalu Singh**

GitHub:  
https://github.com/ss2607

---

## 📄 License

This project is released under the **MIT License**.