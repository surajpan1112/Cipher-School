# Cipher-School
MCQ Test Platform
Introduction
The MCQ Test Platform is a web-based application that allows students to take multiple-choice question (MCQ) tests. The platform includes user authentication, test administration, automated scoring, and email notifications.

Features
User Authentication: Secure login and registration using email and password.
MCQ Test Interface: Dynamic UI for answering MCQ questions with real-time camera preview for proctoring.
Test Submission and Evaluation: Automatic scoring of tests and email notifications to users.
Cron Jobs: Automated hourly evaluation of submitted tests.
Technologies Used
Frontend: React.js
Backend: Node.js with Express
Database: MongoDB
Authentication: JWT (JSON Web Tokens)
Email Service: Nodemailer
Cron Jobs: node-cron
Getting Started
Prerequisites
Node.js and npm installed on your machine.
MongoDB installed and running locally or accessible via a cloud service like MongoDB Atlas.
Installation
Clone the repository:

bash
Copy code
git clone https://github.com/yourusername/mcq-test-platform.git
cd mcq-test-platform
Backend Setup:

Navigate to the backend directory:

bash
Copy code
cd backend
Install backend dependencies:

bash
Copy code
npm install
Create a .env file in the backend directory and add the following environment variables:

bash
Copy code
touch .env
.env content:

makefile
Copy code
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
EMAIL_USER=your_email@example.com
EMAIL_PASS=your_email_password
Start the backend server:

bash
Copy code
node server.js
Frontend Setup:

Navigate to the frontend directory:

bash
Copy code
cd ../frontend
Install frontend dependencies:

bash
Copy code
npm install
Start the React development server:

bash
Copy code
npm start
The frontend will automatically open in your default browser at http://localhost:3000.

Usage
Register and Login:

Access the platform at http://localhost:3000.
Register a new user or log in with existing credentials.
Take a Test:

After logging in, start a new test.
Grant camera and microphone permissions when prompted.
Answer the MCQ questions and navigate freely between them.
Submit the test once completed.
View Results:

The test will be evaluated automatically by a cron job running every hour.
You will receive an email with your score.
Project Structure
plaintext
Copy code
mcq-test-platform/
├── backend/
│   ├── config/
│   │   └── db.js
│   ├── controllers/
│   │   ├── userController.js
│   │   └── testController.js
│   ├── models/
│   │   ├── userModel.js
│   │   ├── testModel.js
│   │   └── resultModel.js
│   ├── routes/
│   │   ├── userRoutes.js
│   │   └── testRoutes.js
│   ├── middleware/
│   │   └── authMiddleware.js
│   ├── .env
│   └── server.js
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   │   ├── CameraPreview.js
│   │   │   └── MCQTest.js
│   │   ├── pages/
│   │   │   ├── LoginPage.js
│   │   │   ├── RegisterPage.js
│   │   │   ├── TestPage.js
│   │   │   └── FinishPage.js
│   │   ├── App.js
│   │   └── index.js
├── package.json
└── README.md
Cron Job for Test Evaluation
The platform includes a cron job that runs every hour to evaluate submitted tests and send the results to users via email.
The cron job is set up using node-cron and can be found in the server.js file.
Email Notifications
Email notifications are sent using Nodemailer.
Configure your email credentials in the .env file under EMAIL_USER and EMAIL_PASS.
