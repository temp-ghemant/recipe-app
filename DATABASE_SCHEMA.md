# Database Schema

## Overview
The application uses a PostgreSQL database with Drizzle ORM. The schema is defined in `shared/schema.ts`.

## Tables

### Users
```
users {
  id: serial (PK)
  username: text (unique)
  password: text (hashed)
  isAdmin: boolean
}
```

### Ingredients
```
ingredients {
  id: serial (PK)
  name: text
  category: text
  isPopular: boolean
  imageUrl: text (nullable)
}
```

### Recipes
```
recipes {
  id: serial (PK)
  title: text
  description: text
  imageUrl: text
  instructions: text
  prepTime: integer
  cookTime: integer
  servings: integer
  calories: integer
  difficulty: text
  cuisine: text
  diet: text
  authorId: integer (FK to users.id)
  authorName: text
  authorAvatar: text
  rating: numeric
  reviewCount: integer
}
```

### Recipe Ingredients
```
recipe_ingredients {
  id: serial (PK)
  recipeId: integer (FK to recipes.id)
  ingredientId: integer (FK to ingredients.id)
  amount: text
  unit: text
}
```

## Relationships
- A Recipe has many Ingredients through Recipe_Ingredients
- An Ingredient can be used in many Recipes through Recipe_Ingredients
- A User can create many Recipes

## Types
For each table, we define:
- Insert Schema: Using `createInsertSchema` from drizzle-zod
- Insert Type: Using `z.infer<typeof insertSchema>`
- Select Type: Using `typeof table.$inferSelect`