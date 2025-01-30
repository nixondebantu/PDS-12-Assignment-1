# Recipe Management System

A comprehensive Python-based recipe management system that allows users to manage, search, and organize recipes through a command-line interface.

## Features

1. **Recipe Management**

   - Add new recipes
   - Update existing recipes
   - Delete recipes
   - View all recipes

2. **Search Capabilities**

   - Search by recipe name
   - Search by cuisine type
   - Search by ingredient
   - Filter by preparation time

3. **Shopping List Generation**

   - Generate shopping lists for selected recipes
   - Account for available ingredients
   - Get sorted list of needed ingredients

4. **Recipe Information Storage**
   - Recipe ID (automatically generated)
   - Recipe Name
   - Ingredients (comma-separated)
   - Preparation Steps
   - Cuisine Type
   - Preparation Time (in minutes)

## Technical Details

### Dependencies

- pandas
- typing
- csv
- datetime

### Class Structure

#### RecipeManager Class

Main class that handles all recipe-related operations:

```python
RecipeManager(csv_file: str)
```

**Key Methods:**

- `add_recipe(recipe_data: Dict) -> bool`
- `update_recipe(recipe_id: str, updated_data: Dict) -> bool`
- `delete_recipe(recipe_id: str) -> bool`
- `search_by_name(name: str) -> pd.DataFrame`
- `search_by_cuisine(cuisine: str) -> pd.DataFrame`
- `search_by_ingredient(ingredient: str) -> pd.DataFrame`
- `filter_by_time(max_time: int) -> pd.DataFrame`
- `get_unique_ingredients() -> List[str]`
- `generate_shopping_list(recipe_ids: List[str], available_ingredients: List[str] = None) -> List[str]`

### Data Storage

- Recipes are stored in a CSV file
- Each recipe has a unique ID in format 'RXXX' (e.g., R001)

## Usage

### Main Menu Options

1. Add New Recipe
2. Update Recipe
3. Delete Recipe
4. Search Recipes
5. Generate Shopping List
6. View All Recipes
7. View Unique Ingredients
8. Exit

### Example Operations

1. **Adding a Recipe**

   ```
   Enter recipe name: Spaghetti Carbonara
   Enter ingredients (comma-separated): spaghetti, eggs, pecorino cheese, pancetta, black pepper
   Enter preparation steps: Boil pasta, Cook pancetta, Mix eggs and cheese, Combine all
   Enter cuisine type: Italian
   Enter preparation time (minutes): 25
   ```

2. **Searching Recipes**

   - By Name: Partial or full recipe name
   - By Cuisine: Type of cuisine
   - By Ingredient: Search for recipes containing specific ingredients
   - By Time: Maximum preparation time

3. **Generating Shopping List**
   ```
   Enter Recipe IDs (comma-separated): R001,R002
   Enter available ingredients (optional): eggs, pasta
   ```

## Implementation Details

### Recipe Data Structure

```python
{
    'Recipe ID': 'R001',
    'Recipe Name': 'Spaghetti Carbonara',
    'Ingredients': 'spaghetti, eggs, pecorino cheese, pancetta, black pepper',
    'Steps': 'Boil pasta, Cook pancetta, Mix eggs and cheese, Combine all',
    'Cuisine': 'Italian',
    'Preparation Time': 25
}
```

### Error Handling

- Input validation for recipe data
- Error handling for file operations
- Protection against duplicate recipe IDs
- Validation of preparation time input

## Best Practices

1. All recipe IDs are automatically generated
2. Ingredients and steps are stored as comma-separated strings
3. Preparation time is stored as integers
4. Case-insensitive search operations
5. Automatic saving of changes to CSV file

## Limitations

1. Single user system
2. No quantity management for ingredients
3. No categorization beyond cuisine type
4. Text-based interface only
