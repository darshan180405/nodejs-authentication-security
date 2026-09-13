# Node.js Authentication & Security

A secure authentication web application built using Node.js, Express.js, PostgreSQL, Passport.js, bcrypt, and EJS.

## Features

- User registration and login
- Password hashing using bcrypt
- Session-based authentication
- Protected routes using Passport.js
- Google OAuth 2.0 authentication
- User logout functionality
- User-specific secret storage
- PostgreSQL database integration
- Environment variables for sensitive configuration

## Technologies Used

- Node.js
- Express.js
- PostgreSQL
- Passport.js
- Passport Local Strategy
- Google OAuth 2.0
- bcrypt
- express-session
- EJS
- HTML
- CSS

## Authentication Flow

### Local Authentication

1. User registers with an email and password.
2. The password is hashed using bcrypt.
3. The hashed password is stored in PostgreSQL.
4. During login, the entered password is compared with the stored hash.
5. Passport.js creates an authenticated session.
6. Authenticated users can access protected routes.

### Google Authentication

Users can also authenticate using their Google account through Google OAuth 2.0.

If the user's Google email does not already exist in the database, a new user record is created.

## Secrets

Authenticated users can submit a personal secret.

The secret is stored in PostgreSQL and associated with the user's email. Users can access their secret only after authentication.

## Database

The application uses PostgreSQL to store user information.

Example user data:

- `id`
- `email`
- `password`
- `secrets`

## Environment Variables

Create a `.env` file in the project root:

```env
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
SESSION_SECRET=your_session_secret

PG_USER=postgres
PG_HOST=localhost
PG_DATABASE=your_database
PG_PASSWORD=your_database_password
PG_PORT=5432
