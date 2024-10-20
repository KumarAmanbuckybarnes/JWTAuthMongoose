# JWTAuthMongoose

 

---

# Node.js Backend Authentication & Role-Based Access Control

This project is a Node.js backend application that implements a secure authentication and authorization system using **JSON Web Tokens (JWT)**, **bcrypt** password hashing, and **role-based access control** for routes (e.g., Student, Admin). The backend connects to a **MongoDB** database using **Mongoose**, and uses **Express** as the web framework.

## Features

- **User Authentication**: Secure login and signup functionality with encrypted passwords using bcrypt.
- **JWT Authorization**: Routes protected with JWT to validate users and their roles.
- **Role-Based Access Control**: Routes protected based on user roles (Student, Admin).
- **MongoDB Integration**: Database connection and schema management using Mongoose.
- **Middleware Functions**: Modular middleware to handle JWT validation and user role checks.
- **Express Framework**: Handling HTTP requests, with cookie parsing and JSON body parsing.

## Project Structure

```
.
├── config
│   └── database.js          # MongoDB connection setup using Mongoose
├── controllers
│   └── Auth.js              # Handles user login and signup requests
├── middleware
│   └── auth.js              # JWT validation and role-based access control middleware
├── models
│   └── User.js              # Defines User schema for MongoDB
├── routes
│   └── user.js              # Routes for login, signup, and role-protected routes
├── index.js                 # Main Express app setup, routes, middleware, database connection
└── package.json             # Project dependencies and scripts
```

### File Descriptions

- **`index.js`**:  
  The entry point of the application. It creates the Express app, sets up middleware, connects to the MongoDB database, and defines routes.

- **`config/database.js`**:  
  Exports a function that establishes a connection to the MongoDB database using Mongoose.

- **`routes/user.js`**:  
  Defines the user-related routes for login, signup, and protected routes. It includes middleware functions to check JWT and user roles.

- **`models/User.js`**:  
  Defines the User schema using Mongoose. It includes fields like username, email, password, and role (Student, Admin).

- **`middleware/auth.js`**:  
  Exports middleware functions to validate JWT and check the user's role for protected routes.

- **`controllers/Auth.js`**:  
  Contains functions for handling user signup and login requests, including password hashing and JWT generation.

## Installation & Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/project-name.git
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file to store your environment variables like MongoDB connection string and JWT secret:
   ```bash
   MONGO_URI=your_mongodb_connection_string
   JWT_SECRET=your_jwt_secret
   ```

4. Start the server:
   ```bash
   npm start
   ```

5. The server will start at `http://localhost:3000`.

## API Endpoints

- **POST** `/signup`  
  Allows a new user to register. The password will be hashed using bcrypt.

- **POST** `/login`  
  Allows an existing user to log in. Returns a JWT for future authenticated requests.

- **Protected Routes**  
  Accessible only by logged-in users with specific roles (e.g., Admin or Student). The JWT token must be included in the request header.

## Technologies Used

- **Node.js**: JavaScript runtime for building the server-side application.
- **Express.js**: Framework for building RESTful APIs.
- **MongoDB**: NoSQL database to store user data.
- **Mongoose**: ODM library for MongoDB.
- **JWT**: For user authentication and authorization.
- **bcrypt**: For password encryption.
- **dotenv**: To manage environment variables.

## Future Improvements

- Add email verification during user signup.
- Implement password reset functionality.
- Expand role-based access control to include more user roles.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request for any features or bug fixes.



---
