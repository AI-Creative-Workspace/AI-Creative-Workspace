# AI Creative Workspace – Backend Guide

This document provides an overview of the backend architecture and setup instructions for the AI Creative Workspace platform.

---

## Overview

The backend of AI Creative Workspace is built using the following technologies:

- **Node.js (Express.js)** – For creating RESTful API services.
- **MongoDB** – As the primary database for storing user data and content.
- **JWT (JSON Web Token)** – For authentication and authorization.
- **Redis** – For caching frequently accessed data.
- **Winston** – For logging and monitoring.
- **Jest & Supertest** – For backend testing.

---

## Project Structure

The backend directory is organized as follows:

backend/
│
├── config/              # Configuration files (e.g., environment variables)
│   ├── dev.env          # Development environment settings
│   ├── prod.env         # Production environment settings
│
├── controllers/         # Business logic and API handlers
│   ├── authController.js   # User authentication logic
│   ├── contentController.js  # Content management logic
│
├── models/              # Database schema definitions
│   ├── User.js          # User schema
│   ├── Content.js       # Content schema
│
├── routes/              # API route definitions
│   ├── authRoutes.js    # Authentication routes
│   ├── contentRoutes.js # Content management routes
│
├── services/            # External integrations and helpers
│   ├── aiService.js     # Integration with AI agent
│   ├── blockchainService.js # Blockchain interactions
│
├── tests/               # Unit and integration tests
│
├── server.js            # Main server entry point
├── database.js          # Database connection setup
├── package.json         # Project dependencies
├── .env                 # Environment variable settings
├── .gitignore           # Files to ignore in version control
└── README.md            # Backend documentation

---

## Installation

Follow these steps to set up the backend locally:

1. Navigate to the `backend/` directory:

   cd backend

2. Install dependencies:

   npm install

3. Set up environment variables:

   Create a `.env` file in the `backend/` directory and include the following keys:

   PORT=5000  
   MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/mydatabase  
   JWT_SECRET=your_secret_key  
   REDIS_URI=redis://localhost:6379  

4. Start the backend server:

   npm start

---

## Available Scripts

In the project directory, you can run the following commands:

- `npm start` – Runs the server in production mode.
- `npm run dev` – Starts the development server with hot reloading.
- `npm test` – Runs unit and integration tests.
- `npm run lint` – Checks code quality and styling issues.

---

## API Endpoints

Below are some key API endpoints:

1. **User Authentication**
   - `POST /api/auth/register` – Register a new user.
   - `POST /api/auth/login` – Authenticate a user and generate a token.

2. **Content Management**
   - `POST /api/content/create` – Create new AI-generated content.
   - `GET /api/content/:id` – Retrieve content by ID.

3. **Blockchain Integration**
   - `GET /api/blockchain/balance` – Get user's token balance.
   - `POST /api/blockchain/transfer` – Transfer tokens to another user.

---

## Testing

We use **Jest** and **Supertest** for unit and integration testing. To run tests, use the following command:

   npm test

Example test in `tests/auth.test.js`:

```javascript
const request = require('supertest');
const app = require('../server');

test('Should sign up a new user', async () => {
    await request(app)
        .post('/api/auth/register')
        .send({
            email: 'testuser@example.com',
            password: 'Test1234!'
        })
        .expect(201);
});
