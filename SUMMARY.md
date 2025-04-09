# Recipe Application Summary

## Project Overview
This application is a recipe suggestion website that allows users to find recipes based on selected ingredients. It features a clean, user-friendly interface with a focus on vegetarian options and international cuisines including Indian recipes.

## Key Features
- **Ingredient-based Recipe Finding**: Select ingredients from the sidebar to find compatible recipes
- **User Authentication**: Login and registration system with admin privileges for content management
- **Admin Interface**: Admin users can add and manage recipes and ingredients
- **Responsive Design**: Mobile-friendly layout that works on all devices

## Technology Stack
- **Frontend**: React with Tailwind CSS and shadcn UI components
- **Backend**: Express.js with PostgreSQL database
- **ORM**: Drizzle for database operations with TypeScript type safety
- **Authentication**: Passport.js for user authentication with secure password hashing

## Database Schema
- Users: For authentication and authorization
- Ingredients: Categorized ingredients including Indian spices and vegetables
- Recipes: Detailed recipe information with instructions and nutritional data
- Recipe-Ingredients: Junction table linking recipes to their ingredients

## Getting Started
1. Clone the repository
2. Install dependencies with `npm install`
3. Set up PostgreSQL database and update environment variables
4. Run the development server with `npm run dev`
5. Access the application at `http://localhost:5000`

## Login Credentials
- Admin User: username: `admin`, password: `admin123`
- Regular User: username: `user`, password: `user123`