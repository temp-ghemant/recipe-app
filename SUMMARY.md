# Recipe App - Project Summary

## Project Overview
This application is a dynamic recipe discovery platform that empowers users to explore culinary possibilities through intelligent ingredient-based search and personalized recipe recommendations. It allows users to find recipes based on available ingredients, browse recipes by category, and save their favorite recipes.

## Key Features
1. **Ingredient-Based Recipe Search**: Find recipes based on ingredients you have available
2. **User Authentication**: Secure login and registration with role-based permissions
3. **Admin Dashboard**: Add and manage ingredients and recipes (admin-only)
4. **Responsive Design**: Works seamlessly on desktop, tablet, and mobile devices
5. **Recipe Details**: View detailed recipe information including ingredients, instructions, and nutritional info
6. **International Cuisines**: Wide variety of recipes from different cuisines with a focus on vegetarian options

## Technology Stack
- **Frontend**: React, Tailwind CSS, shadcn/ui components
- **Backend**: Express.js, Node.js
- **Database**: PostgreSQL with Drizzle ORM
- **Authentication**: Passport.js with local strategy
- **State Management**: React Query for data fetching and caching
- **Routing**: Wouter for client-side routing

## User Roles
1. **Admin Users**:
   - Add, edit, and delete ingredients
   - Add, edit, and delete recipes
   - Access to admin dashboard

2. **Regular Users**:
   - Browse and search recipes
   - Filter recipes based on ingredients
   - View detailed recipe information

## Project Structure
- **Data Model**: Well-defined schema for users, ingredients, recipes, and their relationships
- **Frontend Routes**:
  - `/`: Home page with recipe browsing
  - `/auth`: Login and registration page
  - `/recipe/:id`: Detailed recipe view
  - `/admin`: Admin dashboard (protected route)
- **API Endpoints**:
  - User authentication: `/api/login`, `/api/register`, `/api/logout`
  - Ingredients: `/api/ingredients`, `/api/ingredients/:id`
  - Recipes: `/api/recipes`, `/api/recipes/:id`, `/api/recipes/by-ingredients`

## Next Steps
- Add recipe favoriting functionality
- Implement user reviews and ratings for recipes
- Enhance recommendation system based on user preferences
- Add nutritional information calculation
- Integrate meal planning capabilities