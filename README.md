# Secrets App

A simple secret-sharing web app built with Node.js, Express, PostgreSQL, and Passport.js.  
Users can register/login with email/password or Google OAuth, submit secrets, and view their own secrets anonymously.

---

## Features

- User registration and login with email/password  
- Google OAuth 2.0 sign-in integration  
- Password hashing with bcrypt  
- Session management with express-session  
- Store secrets in PostgreSQL database  
- Secure authentication using Passport.js (local and Google strategies)  
- EJS templating with Bootstrap 4 styling  

---

## Prerequisites

- Node.js (v14 or newer recommended)  
- PostgreSQL database  
- Google OAuth credentials (client ID and secret)  
- Git (optional)  

---

## Getting Started

### 1. Clone the repository
```bash
git clone <your-repo-url>
cd <your-repo-folder>
```
2. Install dependencies
```bash
npm install
```
3. Set up PostgreSQL database

Create a database and a users table:
```bash
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  email VARCHAR(255) UNIQUE NOT NULL,
  password VARCHAR(255),
  secret TEXT
);
```

4. Configure environment variables
Create a .env file in the root directory and add the following (see .env.example for reference):
```bash
SESSION_SECRET=your_session_secret
PG_USER=your_pg_user
PG_HOST=localhost
PG_DATABASE=your_database
PG_PASSWORD=your_password
PG_PORT=5432
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
```
Replace values with your actual credentials.

Make sure to get Google OAuth credentials from Google Developer Console
.

5. Run the application
```bash
npm start
```
The server will start on http://localhost:3000.



## Usage

Visit http://localhost:3000 to see the home page.

Register a new account or sign in with Google.

Submit your secret anonymously.

View your submitted secret or log out.



## Project Structure

app.js — Main server file

views/ — EJS templates (includes partials for header and footer)

public/ — Static assets (CSS, JS, images)

.env — Environment variables (not committed to git)



## Dependencies

express

body-parser

pg

bcrypt

passport

passport-local

passport-google-oauth2

express-session

dotenv

ejs



## License

MIT License © Sandeep Rana



## Acknowledgements

Inspired by authentication tutorials using Passport.js and PostgreSQL.

Bootstrap and FontAwesome for UI components.

---


## 🛠 `.env.example`

```dotenv
SESSION_SECRET=your_session_secret
PG_USER=your_pg_user
PG_HOST=localhost
PG_DATABASE=your_database
PG_PASSWORD=your_password
PG_PORT=5432
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
```


## 🧩 SQL Schema for users table
```sql
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  email VARCHAR(255) UNIQUE NOT NULL,
  password VARCHAR(255),
  secret TEXT
);
```
