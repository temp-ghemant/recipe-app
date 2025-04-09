# Database Schema Documentation

## Overview
This document outlines the database schema used in the Recipe App. The application uses PostgreSQL with Drizzle ORM for data persistence. The schema is defined in `shared/schema.ts`.

## Tables

### Users
Stores user authentication and profile information.

| Column | Type | Description |
|--------|------|-------------|
| id | Serial | Primary key, auto-incrementing |
| username | Text | Unique username for login |
| password | Text | Hashed password (scrypt) |
| email | Text | User's email address |
| isAdmin | Boolean | Whether the user has admin privileges |
| createdAt | Timestamp | When the user account was created |

### Ingredients
Stores information about recipe ingredients.

| Column | Type | Description |
|--------|------|-------------|
| id | Serial | Primary key, auto-incrementing |
| name | Text | Ingredient name |
| category | Text | Category (e.g., vegetables, grains, spices) |
| imageUrl | Text | Optional URL to ingredient image |
| isPopular | Boolean | Whether this is a commonly used ingredient |
| createdAt | Timestamp | When the ingredient was added |

### Recipes
Stores recipe information.

| Column | Type | Description |
|--------|------|-------------|
| id | Serial | Primary key, auto-incrementing |
| title | Text | Recipe title |
| description | Text | Brief recipe description |
| instructions | Text | Step-by-step cooking instructions |
| imageUrl | Text | URL to recipe image |
| prepTime | Integer | Preparation time in minutes |
| cookTime | Integer | Cooking time in minutes |
| servings | Integer | Number of servings |
| difficulty | Text | Difficulty level (easy, medium, hard) |
| cuisine | Text | Type of cuisine (Indian, Italian, etc.) |
| diet | Text | Dietary categorization (vegetarian, vegan, etc.) |
| authorId | Integer | Foreign key to the users table |
| calories | Integer | Caloric content per serving |
| createdAt | Timestamp | When the recipe was added |

### Recipe Ingredients
Junction table linking recipes to their ingredients with quantities.

| Column | Type | Description |
|--------|------|-------------|
| id | Serial | Primary key, auto-incrementing |
| recipeId | Integer | Foreign key to the recipes table |
| ingredientId | Integer | Foreign key to the ingredients table |
| amount | Text | Amount needed (e.g., "2 cups", "1 tablespoon") |
| isOptional | Boolean | Whether the ingredient is optional |

## Relationships

### Recipe to Ingredients (Many-to-Many)
- A recipe can have multiple ingredients
- An ingredient can be used in multiple recipes
- The recipe_ingredients table serves as the junction table

### Recipe to User (Many-to-One)
- A recipe belongs to one author (user)
- A user can create multiple recipes

## Indexes
- Username index on users table for fast lookup during authentication
- Category index on ingredients table for efficient filtering
- Cuisine and diet indexes on recipes table for recipe filtering