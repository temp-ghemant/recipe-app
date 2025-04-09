# Installation Guide

## Prerequisites
- Node.js (v18+ recommended)
- PostgreSQL database
- Git

## Steps to Install

### 1. Clone the Repository
```bash
git clone https://github.com/temp-ghemant/recipe-app.git
cd recipe-app
```

### 2. Unzip the Source Code
The source code is included in the repository as a zip file. Extract it:
```bash
# Extract the code archive to get all source files
unzip code_archive.zip
```

### 3. Install Dependencies
```bash
npm install
```

### 4. Set Up Environment Variables
Create a `.env` file in the root directory with the following variables:
```
DATABASE_URL=postgres://username:password@localhost:5432/recipe_app
SESSION_SECRET=your_secure_random_string
```
Replace `username`, `password` with your PostgreSQL credentials.

### 5. Set Up Database
Create a PostgreSQL database:
```bash
createdb recipe_app
```

Then push the schema to the database:
```bash
npm run db:push
```

### 6. Run the Application
```bash
npm run dev
```

The application should now be running at `http://localhost:5000`

## Default User Accounts
The application comes with two default accounts for testing:

1. Admin User
   - Username: `admin`
   - Password: `admin123`

2. Regular User
   - Username: `user`
   - Password: `user123`

## Folder Structure
- `client/`: Frontend React application
- `server/`: Backend Express server
- `shared/`: Shared code between client and server
- `drizzle.config.ts`: Database configuration

## Development Commands
- `npm run dev`: Start development server
- `npm run build`: Build the project for production
- `npm run db:push`: Push schema changes to the database