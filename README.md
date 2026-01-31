# 🎬 GetMySeat - Movie Ticket Booking System

GetMySeat is a full-stack web application that provides a seamless movie ticket booking experience. It allows users to browse movies, select showtimes, book seats in real-time, and make secure payments using Razorpay.

---

## 🌟 Table of Contents

- [Project Overview](#project-overview)
- [Key Features](#key-features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Core Functionalities](#core-functionalities)
- [Installation & Setup](#installation--setup)
- [API Endpoints](#api-endpoints)
- [Database Models](#database-models)
- [Real-Time Features](#real-time-features)
- [Deployment](#deployment)
- [Contributing](#contributing)
- [License](#license)

---

## 📋 Project Overview

GetMySeat is a comprehensive movie ticket booking platform that connects movie enthusiasts with cinema halls across multiple cities. The application features real-time seat availability, secure payment processing, and a user-friendly interface with both customer and admin panels.

---

## 🎯 Key Features

### 👥 User Features
- ✅ **User Registration & Login** - Secure signup with email verification
- ✅ **Movie Browsing** - Browse latest releases, trending, and top-rated movies
- ✅ **Movie Details** - View movie information including cast, director, ratings, genres, languages
- ✅ **Show Timings** - Check available showtimes across different cities and cinemas
- ✅ **Seat Selection** - Interactive visual seat booking with tier-based pricing
- ✅ **Real-Time Seat Availability** - Live seat updates using Socket.io
- ✅ **Secure Payment** - Payment processing via Razorpay
- ✅ **Booking History** - View all past bookings with filtering (Upcoming/Ended)
- ✅ **Booking Cancellation** - Cancel seat bookings before the show starts
- ✅ **Ticket with QR Code** - Digital ticket generation with unique QR codes
- ✅ **User Reviews & Ratings** - Post and view reviews for movies
- ✅ **City Selection** - Browse movies available in selected cities
- ✅ **Trailer Viewing** - Watch movie trailers before booking

### 🏢 Admin Features
- ✅ **Admin Dashboard** - Centralized admin panel for management
- ✅ **Movie Management** - Add, edit, and delete movies
- ✅ **Cinema Management** - Add and manage cinema halls and locations
- ✅ **Show Management** - Create and manage shows and showtimes
- ✅ **Booking Management** - View and manage all user bookings
- ✅ **User Management** - View and manage user accounts
- ✅ **Analytics Dashboard** - Access booking and user statistics

### 💳 Payment & Security
- ✅ **Razorpay Integration** - Secure payment gateway integration
- ✅ **Payment Verification** - Cryptographic verification of payments
- ✅ **Email Notifications** - Booking confirmation emails via Nodemailer
- ✅ **Email Verification** - User account email verification system
- ✅ **Session Management** - Secure session handling with MongoDB store

### 🔍 Additional Features
- ✅ **Search Functionality** - Search movies by title, genre, actor
- ✅ **Multiple Cities Support** - Browse cinemas across 20+ major Indian cities
- ✅ **Responsive Design** - Works seamlessly on desktop and mobile devices
- ✅ **Seat Pricing Tiers** - Gold, Silver, Bronze pricing based on seat location
- ✅ **About Page** - Project information and team details
- ✅ **FAQ Section** - Comprehensive FAQs for user support
- ✅ **Privacy Policy** - Detailed privacy information
- ✅ **Terms & Conditions** - Complete terms of service
- ✅ **Services Page** - Overview of all platform services

---

## 🛠️ Tech Stack

| Component | Technology |
|-----------|-----------|
| **Frontend** | React, React Router, Context API, Socket.io (Client) |
| **Backend** | Node.js, Express.js |
| **Database** | MongoDB with Mongoose ODM |
| **Real-Time** | Socket.io for WebSocket communication |
| **Payment** | Razorpay API |
| **Email** | Nodemailer |
| **Authentication** | Passport.js, JWT |
| **Session Store** | MongoDB Session Store (connect-mongo) |
| **Deployment** | Heroku/Render |
| **Languages** | JavaScript (72.8%), CSS (27.1%), HTML (0.1%) |

---

## 📁 Project Structure


GetMySeat/ ├── Frontend/ # React Frontend │ ├── src/ │ │ ├── pages/ │ │ │ ├── Home/ # Homepage with movie listings │ │ │ ├── Movie/ # Movie detail pages │ │ │ ├── Booking/ # Seat selection & booking │ │ │ ├── User/ # Login, Signup, Profile, Bookings │ │ │ ├── Admin/ # Admin dashboard & management │ │ │ ├── Search/ # Search results │ │ │ └── footer/ # About, Services, FAQ, Privacy, Terms │ │ ├── components/ │ │ │ ├── Layout/ # Header, Footer components │ │ │ ├── MovieInfo/ # Movie information display │ │ │ ├── Booking/ # SeatMatrix, pricing components │ │ │ ├── Buttons/ # Reusable button components │ │ │ └── ... │ │ ├── contexts/ # Context API (User, City) │ │ └── App.jsx # Main app with routing │ └── package.json │ ├── Backend/ # Express Backend │ ├── models/ │ │ ├── user.js # User schema with Passport │ │ ├── movie.js # Movie schema with details │ │ ├── theatre.js # Theatre/Cinema schema │ │ ├── screens.js # Screen schema │ │ ├── shows.js # Show schema with bookings │ │ ├── booking.js # Booking schema │ │ └── review.js # Review/Rating schema │ ├── init/ │ │ └── data.js # Seed data (theatres, shows) │ ├── app.js # Main Express application │ ├── .env # Environment variables │ └── package.json │ └── README.md # This file
Code


---

## 🔧 Core Functionalities

### 1. **Authentication System**
- User registration with email verification
- Secure login/logout with Passport.js
- Password recovery via email
- Email-based account verification

### 2. **Real-Time Seat Booking**
- Socket.io integration for live seat updates
- Seat locking mechanism to prevent double bookings
- Three-tier pricing: Gold (₹400), Silver (₹300), Bronze (₹250)
- Visual feedback for seat states (available, selected, booked)

### 3. **Payment Processing**
- Razorpay payment gateway integration
- Order creation and verification
- Cryptographic signature validation
- Payment status tracking

### 4. **Movie Management**
- Comprehensive movie data with ratings (IMDb, Rotten Tomatoes, Google)
- Movie metadata: cast, director, genres, languages, format
- Background and poster images
- Trailer links

### 5. **Booking Management**
- Create and track bookings
- Booking history with filtering
- Cancellation system with seat release
- QR code generation for tickets

### 6. **Admin Controls**
- Add/Edit/Delete movies
- Manage cinema halls and screens
- Create shows and showtimes
- View all bookings and user analytics

---

## 🚀 Installation & Setup

### Prerequisites
- Node.js (v14 or higher)
- MongoDB (local or Atlas)
- npm or yarn package manager

### Backend Setup

```bash
cd Backend

# Install dependencies
npm install

# Create .env file with required variables
# Add the following:
# MONGO_URL=your_mongodb_connection_string
# PASSWORD=your_email_app_password
# RAZORPAY_KEY_ID=your_razorpay_key
# RAZORPAY_SECRET=your_razorpay_secret

# Start the server
npm start

```

### Frontend Setup
```bash

cd Frontend

# Install dependencies
npm install

# Start the development server
npm start
```


