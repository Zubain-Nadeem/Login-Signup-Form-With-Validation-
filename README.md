This project includes two separate React components for Signup and Login. Both forms appear on the same page. The goal is to practice controlled components, form validation, event handling, and storing user data in localStorage.

The Signup form lets a new user register. The Login form verifies stored user data and allows access only when the email and password match what was saved during signup.

Features
Signup Form

Full Name

Email

Password

Confirm Password

Inline validation messages

Strong password checking

Duplicate email protection

Saves new users to localStorage

Login Form

Email

Password

Validation for both fields

Checks stored data in localStorage

Displays errors for wrong email or password

Validation Rules

All fields required

Valid email format

Password must be at least 8 characters and include uppercase, lowercase, numbers, and a symbol

Password and Confirm Password must match

Login verifies credentials from localStorage

Local Storage Structure

Users are stored using a simple structure:

key: "users"
value: [
  {
    fullName: "User Name",
    email: "user@example.com",
    password: "originalOrHashedPassword"
  }
]


A currentUser entry may also be used after login if needed.

How It Works
Signup

User enters their information.

Validation checks run on blur and on submit.

If valid, the user is saved in localStorage.

Duplicate emails are not allowed.

A success message appears.

Login

User enters email and password.

Data is checked against users saved in localStorage.

If matched, login is successful.

If not, an error message explains the issue.

Project Structure
src/
│ App.jsx
│ index.js
│
├── components/
│   ├── SignupForm.jsx
│   └── LoginForm.jsx
│
├── utils/
│   └── validation.js
│
└── services/
    └── authStorage.js

Installation & Setup

Clone the repository:

Install dependencies:

npm install

Start the development server:

npm run dev


Open the app in your browser (usually http://localhost:5173 for Vite).

Testing

Recommended manual test cases:

Signup Testing

Empty fields show required messages

Invalid email shows error

Weak password rejected

Confirm Password mismatch blocked

Duplicate email prevented

Valid signup saves to localStorage

Login Testing

Wrong email shows “account not found”

Wrong password shows “incorrect password”

Correct credentials show success

localStorage persists after refresh
