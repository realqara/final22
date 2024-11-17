> aiyalap:
README.md for final23
final23 - Portfolio Platform with Air Quality API and 2FA
This project is a Portfolio Platform that allows users to register, log in with Two-Factor Authentication (2FA), and manage portfolio items. The platform also integrates the OpenWeatherMap Air Quality API to fetch air quality data based on latitude and longitude coordinates.

Features
User Registration & Login with 2FA: Users can register and log in with username, password, and 2FA (using an authenticator app like Google Authenticator).
Portfolio Management (CRUD): Admins can manage (create, update, delete) portfolio items. Editors can only create new items.
Air Quality Data: Fetch real-time air quality data using the OpenWeatherMap Air Quality API. Users can view AQI (Air Quality Index) and pollutant levels based on geographic coordinates.
Role-based Access Control: Admins have full access, while editors can only create content.
Responsive Design: The platform is fully responsive and works across different screen sizes (mobile, tablet, desktop).
Technologies Used
Frontend: React, Axios, React Router
Backend: Node.js, Express, MongoDB, JWT (JSON Web Tokens), bcrypt, speakeasy (for 2FA), Nodemailer (for email notifications)
API: OpenWeatherMap Air Quality API
Database: MongoDB (hosted via MongoDB Atlas)
Installation & Setup
1. Clone the Repository
Clone the repository to your local machine:

git clone https://github.com/yourusername/final23.git
2. Set Up the Backend (Node.js/Express)
Navigate to the server directory:

cd server
Install the backend dependencies:

npm install
Create a .env file in the server directory and add the following environment variables:

MONGO_URI=your_mongodb_connection_string_here
JWT_SECRET=your_jwt_secret_here
WEATHER_API_KEY=your_openweathermap_api_key_here
EMAIL_USER=your_email@example.com
EMAIL_PASS=your_email_password
MONGO_URI: Your MongoDB connection string (get it from MongoDB Atlas).
JWT_SECRET: Secret key for JWT tokens.
WEATHER_API_KEY: Your OpenWeatherMap API key.
EMAIL_USER and EMAIL_PASS: Your email credentials for Nodemailer.
Start the backend server:

node app.js
The backend server will run on http://localhost:3000.

3. Set Up the Frontend (React)
Navigate to the client directory:

cd client
Install the frontend dependencies:

npm install
Create a .env file in the client directory and add the following variable:

REACT_APP_API_URL=http://localhost:3000/api
Start the React development server:

npm start
The frontend React app will run on http://localhost:3001.

Usage
1. Register a User
Navigate to the Registration Page (/register).
Enter your username, password, first name, last name, age, gender, and email.
After registration, a QR code will be shown. Scan this QR code with an authenticator app (like Google Authenticator) to set up 2FA.
2. Login
Navigate to the Login Page (/login).
Enter your username, password, and 2FA code (generated from your authenticator app).
If both are correct, you’ll be logged in and redirected to the home page or dashboard.
3. Portfolio Management (CRUD)
If you're an admin, you can create, update, and delete portfolio items.
If you're an editor, you can only create portfolio items, but cannot update or delete them.
4. Air Quality Data
The app allows you to check the Air Quality Index (AQI) and pollutants for any location using its latitude and longitude.
The API call can be made at http://localhost:3000/api/air-quality?lat={lat}&lon={lon}.
Folder Structure
Frontend (React)
client/public/: Public assets (index.html, styles.css)
client/src/: React source code (components, pages, App.js, etc.)
client/package.json: React dependencies and scripts
Backend (Node.js)
server/: Backend code (Express server, API routes, controllers, models)
server/routes/: API routes (authentication, portfolio, air quality)
server/controllers/: Route handling logic (authentication, portfolio CRUD)
server/models/: MongoDB

models (User, Portfolio)
server/app.js: Main entry point for the backend server
Troubleshooting
CORS Issues: If you encounter CORS issues, ensure that your backend server has the cors middleware enabled, as it allows cross-origin requests from the React frontend.
Environment Variables: Ensure that all the necessary environment variables (in .env) are set up correctly for both backend and frontend.
