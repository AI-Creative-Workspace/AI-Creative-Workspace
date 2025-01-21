# AI Creative Workspace – Frontend Guide

This document provides an overview of the frontend architecture and setup instructions for the AI Creative Workspace platform.

---

## Overview

The frontend of AI Creative Workspace is a web-based application built using the following technologies:

- React.js – For building dynamic user interfaces.
- Redux – For state management.
- Styled Components – For styling and component-based design.
- Axios – For API requests and data fetching.
- React Router – For client-side routing.
- Jest & React Testing Library – For unit and integration testing.

---

## Project Structure

The frontend directory is organized as follows:

frontend/
│
├── public/              # Static assets (favicon, manifest, index.html)
│   ├── favicon.ico      # Application icon
│   ├── index.html       # Main HTML template
│   ├── manifest.json    # Web app manifest
│
├── src/                 # Source code for the frontend
│   ├── components/      # Reusable UI components
│   ├── pages/           # Page components (e.g., Home, Dashboard)
│   ├── redux/           # State management setup (actions, reducers, store)
│   ├── services/        # API integration and service calls
│   ├── utils/           # Utility functions
│   ├── assets/          # Images, icons, fonts, styles
│   ├── App.js           # Root component
│   ├── index.js         # Entry point
│
├── tests/               # Unit and integration tests
│
├── package.json         # Project dependencies
├── .env                 # Environment variables
├── .gitignore           # Ignored files for version control
└── README.md            # Frontend documentation

---

## Installation

Follow these steps to set up the frontend locally:

1. Navigate to the `frontend/` directory:

   cd frontend

2. Install dependencies:

   npm install

3. Set up environment variables:

   Create a `.env` file in the `frontend/` directory and include the following keys:

   REACT_APP_API_URL=https://api.aicreativeworkspace.com/v1
   REACT_APP_API_KEY=your_api_key_here

4. Start the development server:

   npm start

---

## Available Scripts

In the project directory, you can run the following commands:

- `npm start` – Runs the app in development mode.
- `npm test` – Runs unit and integration tests.
- `npm run build` – Builds the app for production.
- `npm run lint` – Checks code quality and styling issues.

---

## API Integration

The frontend communicates with the backend API via Axios. Example API call in `services/api.js`:

import axios from 'axios';

const API_URL = process.env.REACT_APP_API_URL;

export const fetchContent = async () => {
    try {
        const response = await axios.get(`${API_URL}/content`);
        return response.data;
    } catch (error) {
        console.error('API Error:', error);
        throw error;
    }
};

---

## Deployment

The frontend can be deployed using any static site hosting services such as:

1. Vercel – Automated deployments from GitHub.
2. Netlify – CI/CD pipeline for React apps.
3. AWS S3 – Deployment via AWS cloud.

To build the project for deployment, run:

   npm run build

This command creates an optimized production build in the `build/` directory.

---

## Testing

We use Jest and React Testing Library for testing. To run tests, use the following command:

   npm test

---

## Contribution

If you'd like to contribute to the frontend, follow the guidelines outlined in `docs/CONTRIBUTING.md`.

---

## Contact

For frontend-related inquiries, please contact the development team at:

Email: frontend@aicreativeworkspace.com  
Discord: [Join our community](#)

---

Thank you for contributing to AI Creative Workspace!
