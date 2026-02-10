# Wheel Data Manager

A small Node.js/Express application for managing student and fee data with Handlebars views and MongoDB persistence.

## Features
- User authentication (login/signup)
- Session-based access control
- Student and fee management dashboards (aggregations + charts)
- Image upload support (Multer, stored in MongoDB as binary)
- Dynamic database connection switching per user

## Tech stack
- Node.js
- Express
- Handlebars (`hbs` / `express-handlebars`)
- MongoDB (Mongoose)
- Multer (file uploads)
- bcryptjs (password hashing)

## Prerequisites
- Node.js (14+ recommended)
- A MongoDB instance or Atlas cluster

## Quickstart
1. Install dependencies:

```bash
npm install
```

2. Configure your MongoDB connection. The app currently contains a hard-coded connection string in `src/app.js`. For security, replace that with an environment variable before deploying. Example using PowerShell:

```powershell
$env:MONGODB_URI = "your_mongo_connection_string"
```

3. Start the app:

```bash
npm start
```

The app listens on port `4000` by default. Open http://localhost:4000

## Important notes
- The repository currently contains a direct MongoDB connection string in `src/app.js`. Remove any embedded credentials and use an environment variable such as `MONGODB_URI` instead.
- Passwords must be hashed before saving; verify `models/user.js` uses `bcryptjs` correctly.
- Static assets are served from the `public/` folder, and views are in `templates/views/`.

## Project structure (key files)
- `src/app.js` — main Express app and route definitions
- `src/db/connection.js` — helper for connecting to a database
- `src/models/user.js` — Mongoose models (users, students, fees)
- `public/` — static assets
- `templates/views/` — Handlebars templates

## Running in development
- Set your environment variables, then run `npm start`. Consider using `nodemon` for auto-reload during development.

## Contributing
- Fix bugs, improve security (remove hard-coded credentials), and add README examples or tests.

## License
This project has no license specified. Add a `LICENSE` file (e.g., MIT) if you want to allow reuse.
