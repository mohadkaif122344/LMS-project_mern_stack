# 📚 LMS Platform (Learning Management System)

A full-stack Learning Management System built with **MERN Stack**, **Clerk Authentication**, and **Stripe Payments**.  
This platform allows educators to create and sell courses, and students to enroll, preview lectures, and track progress.

---

## Demo Live : https://lms-project-mern-stackproject.vercel.app/
<img width="1916" height="1014" alt="Screenshot 2026-01-20 152656" src="https://github.com/user-attachments/assets/360e9a53-1bdc-46b5-99b4-58136a26bb21" />

## Features

### Educator
- Become an educator (role based)
- Create & publish courses
- Add chapters and lectures
- Mark lectures as **Free Preview / Paid**
- Upload course thumbnails (Cloudinary)
- View dashboard (earnings, enrollments)
- View enrolled students

###  Student
- Browse all published courses
- View course details
- Watch **free preview lectures**
- Purchase courses using **Stripe Checkout**
- View enrolled courses
- Track course progress
- Rate courses after purchase

### 🔐 Authentication
- Secure authentication using **Clerk**
- Role-based access (Student / Educator)
- Webhook sync between Clerk & MongoDB

### 💳 Payments
- Stripe Checkout integration
- Secure webhook handling
- Purchase status tracking (pending / completed / failed)

---

## 🛠 Tech Stack

### Frontend
- React (Vite)
- React Router DOM
- Context API
- Axios
- Tailwind CSS
- React Toastify
- Quill Editor
- YouTube Player

### Backend
- Node.js
- Express.js
- MongoDB + Mongoose
- Clerk (Auth)
- Stripe (Payments)
- Cloudinary (Images)
- Multer (File upload)


---

## 🔑 Environment Variables

### Backend (`.env`)
```base
CURRENCY='USD' 

MONGO_URI=your_mongodb_uri

CLERK_PUBLISHABLE_KEY=
CLERK_SECRET_KEY=your_clerk_secret
CLERK_WEBHOOK_SECRET=your_clerk_webhook_secret

STRIPE_PUBLISHABLE_KEY =
STRIPE_SECRET_KEY=your_stripe_secret
STRIPE_WEBHOOK_SECRET=your_stripe_webhook_secret

CLOUDINARY_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_cloudinary_key
CLOUDINARY_SECRET_KEY=your_cloudinary_secret

```
### Frontend (`.env`)
```bash
VITE_CURRENCY = '$'
VITE_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key

VITE_BACKEND_URL=http://localhost:5000


```

## ▶️ How to Run Locally

### 1️⃣ Clone Repository
```bashe
git clone https://github.com/your-username/LMS-project_mern_stack
.git
cd LMS-project_mern_stack

```
2️⃣ Backend Setup
```
cd backend
npm install
npm run dev
```
🚀 Deployment (Vercel)
🔹 Frontend Deployment

Push code to GitHub

Go to Vercel → New Project

Select repository

Root Directory → frontend

Build Command → npm run build

Output Directory → dist

Add frontend environment variables

Deploy 🎉

🔹 Backend Deployment

Add vercel.json inside backend/
```bash
{
  "version": 2,
  "builds": [
    { "src": "server.js", "use": "@vercel/node" }
  ],
  "routes": [
    { "src": "/(.*)", "dest": "/server.js" }
  ]
}
