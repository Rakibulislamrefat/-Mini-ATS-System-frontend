# Mini ATS System

A comprehensive Applicant Tracking System (ATS) built with the MERN stack (MongoDB, Express, React, Node.js) and TypeScript. This system streamlines the recruitment process, from candidate import to interview scheduling and hiring decisions.

## 🚀 Features

- **Authentication**: Secure Login and Registration for Staff and Candidates.
- **Dashboard**: Real-time overview of candidate status, interview statistics, and recent activities.
- **Candidate Management**:
    - **Import**: Bulk import candidates via Excel files with column mapping validation.
    - **View & Filter**: Advanced filtering and search capabilities for candidate lists.
    - **Details**: Comprehensive candidate profiles with status tracking.
- **Interview Management**:
    - **Scheduling**: Schedule interviews with automated status updates.
    - **Workflow**: Manage First and Second Round interviews distinctively.
    - **Results**: Track interview outcomes (Passed/Failed/Pending).
- **Data Export**: Download candidate phone numbers and details for external processing.
- **Responsive Design**: Fully optimized for desktop and mobile devices.

## 🛠 Tech Stack

### Frontend
- **Framework**: React 18+ with Vite
- **Language**: TypeScript
- **Styling**: Tailwind CSS, Shadcn UI (Radix UI primitives)
- **State Management**: Redux Toolkit
- **Routing**: React Router DOM
- **HTTP Client**: Axios
- **Utilities**: Lucide React (Icons), XLSX (Excel processing)

### Backend
- **Runtime**: Node.js
- **Framework**: Express.js
- **Database**: MongoDB with Mongoose ODM
- **Authentication**: JWT (JSON Web Tokens)
- **File Handling**: Multer (for file uploads)

## 📂 Project Structure

```
Mini_ATS_system/
├── backend/            # Node.js/Express API server
│   ├── src/
│   │   ├── config/     # Database and environment config
│   │   ├── controllers/# Business logic for routes
│   │   ├── middleware/ # Auth and error handling middleware
│   │   ├── models/     # Mongoose data models
│   │   ├── routes/     # API route definitions
│   │   └── app.js      # App entry point
│   └── ...
└── frontend/           # React application
    ├── src/
    │   ├── components/ # Reusable UI components (Layout, Shared, UI)
    │   ├── features/   # Redux slices for state management
    │   ├── lib/        # Utilities (API client, Validators)
    │   ├── pages/      # Application route pages
    │   └── types/      # TypeScript interfaces
    └── ...
```

## ⚙️ Installation & Setup

### Prerequisites
- Node.js (v18 or higher recommended)
- MongoDB (Local instance or MongoDB Atlas connection string)
- Git

### 1. Clone the Repository
```bash
git clone <repository-url>
cd Mini_ATS_system
```

### 2. Backend Setup
Navigate to the backend directory and install dependencies:
```bash
cd backend
npm install
```

Create a `.env` file in the `backend` directory:
```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_strong_jwt_secret
CLIENT_URL=http://localhost:5173
```

Start the backend server:
```bash
npm run dev
```
The server will run on `http://localhost:5000`.

### 3. Frontend Setup
Open a new terminal, navigate to the frontend directory, and install dependencies:
```bash
cd frontend
npm install --legacy-peer-deps
```
*Note: `--legacy-peer-deps` is required for compatibility with some packages in the current environment.*

Create a `.env` file in the `frontend` directory:
```env
VITE_API_URL=http://localhost:5000/api
```

Start the frontend development server:
```bash
npm run dev
```
The application will be available at `http://localhost:5173`.

## 📝 Development Workflow

### Version Control
- **Git Repository**: Initialize and maintain a Git repository.
- **Commits**: Commit code regularly with clear, descriptive messages (e.g., `feat: add candidate import`, `fix: resolve login error`).
- **Branches**: Use feature branches for new tasks to keep `main` stable.

### Frontend-Backend Integration
- Ensure the **Backend** is running before interacting with the Frontend.
- Use the configured `api-client.ts` in `frontend/src/lib` for all API requests to handle base URLs and authentication tokens automatically.

### Styling & UI
- Use **Tailwind CSS** for layout and styling (utility-first approach).
- Leverage **Shadcn UI** components located in `src/components/ui` for consistent design patterns (Buttons, Inputs, Cards, etc.).
- Ensure responsiveness by testing on different viewport sizes using browser dev tools.

### Testing & Quality
- **Responsiveness**: Verify UI on Mobile, Tablet, and Desktop views.
- **Error Handling**: Test edge cases (e.g., invalid inputs, network errors) to ensure the UI fails gracefully with user-friendly messages.
- **Linting**: Run linting commands to catch code quality issues early.
