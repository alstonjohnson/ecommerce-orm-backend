# E-commerce Back End

This project implements the back end of an e-commerce site using Express.js and Sequelize to interact with a PostgreSQL database. The application is designed to handle API requests for managing product, category, and tag data, allowing CRUD operations across these entities. The application demonstrates essential back-end functionalities that support an e-commerce site’s data management needs.

## User Story

As a manager at an internet retail company, I need a back end for my e-commerce website that uses the latest technologies so that my company can compete effectively with other e-commerce companies.

## Acceptance Criteria

1. A functional Express.js API that connects to a PostgreSQL database using Sequelize.
2. Environment variables store database credentials.
3. Database schema and seed data are initialized with commands.
4. Server starts and Sequelize models sync with the database.
5. API GET routes display formatted JSON for categories, products, and tags in Insomnia Core.
6. API POST, PUT, and DELETE routes create, update, and delete data in the database.

## Database Models

- **Category**: `id` (PK), `category_name`
- **Product**: `id` (PK), `product_name`, `price`, `stock`, `category_id` (FK)
- **Tag**: `id` (PK), `tag_name`
- **ProductTag**: `id` (PK), `product_id` (FK), `tag_id` (FK)

### Associations
- `Product` belongs to `Category`.
- `Category` has many `Products`.
- `Product` belongs to many `Tags` (through `ProductTag`).
- `Tag` belongs to many `Products`.

## Setup

1. Clone this repository and install dependencies:
   ```bash
   git clone <your-repo-url>
   cd <project-directory>
   npm install
Create a .env file and add PostgreSQL credentials:
DB_NAME='your_db_name'
DB_USER='your_username'
DB_PASSWORD='your_password'
Initialize and seed the database:
psql -f db/schema.sql
npm run seed
Start the server:
npm start
Usage

Use Insomnia Core to test API endpoints for categories, products, and tags.

GET routes display all categories, products, and tags or a single item by ID.
POST, PUT, and DELETE routes create, update, and delete items in the database.
Walkthrough Video

Check out the walkthrough video demonstrating the application’s functionality, including all API endpoints in action.

Technologies

Node.js
Express.js
PostgreSQL
Sequelize
dotenv