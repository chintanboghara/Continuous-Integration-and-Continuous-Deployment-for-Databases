# Node.js PostgreSQL Todo Application

This is a Node.js application that demonstrates how to manage database migrations with PostgreSQL using `node-pg-migrate`.

## Features

- Integration with a PostgreSQL database
- Database migrations using `node-pg-migrate`
- Environment-based configuration
- A straightforward todo management system

## Prerequisites

- Node.js (version 14 or higher)
- PostgreSQL database server
- npm (Node Package Manager)

## Project Structure

```
├── migrations/
│   └── 1698765432345_create-todos-table.js
├── .env.example
├── .env
├── index.js
├── package.json
└── README.md
```

## Setup Instructions

1. Clone the repository.
2. Install the dependencies:
   ```bash
   npm install
   ```
3. Create a `.env` file based on the provided `.env.example`:
   ```bash
   cp .env.example .env
   ```
4. Update the `.env` file with your PostgreSQL connection details:
   ```
   DATABASE_URL=postgres://username:password@localhost:5432/database_name
   ```

## Database Migrations

This project uses `node-pg-migrate` to manage database schema changes.

### Available Migration Commands

- To run all pending migrations:
  ```bash
  npm run migrate:up
  ```
- To revert the last migration:
  ```bash
  npm run migrate:down
  ```

### Current Migrations

1. `1698765432345_create-todos-table.js`
   - This migration creates the initial `todos` table with the following fields:
     - `id` (Primary Key)
     - `title` (varchar)
     - `completed` (boolean)
     - `created_at` (timestamp)

## Running the Application

To start the application, run:
```bash
npm start
```

Once started, the application will:
1. Connect to the PostgreSQL database
2. Display the current timestamp
3. List all todos stored in the database

## Environment Variables

| Variable      | Description                | Example                                           |
|---------------|----------------------------|---------------------------------------------------|
| DATABASE_URL  | PostgreSQL connection URL  | postgres://username:password@localhost:5432/todos |

## Security Notes

- Never commit the `.env` file to version control.
- Keep your database credentials secure.
- The `.env.example` file should not contain actual credentials.

## Scripts

- `npm start` - Runs the application.
- `npm run migrate` - Executes database migrations.
- `npm run migrate:up` - Applies any pending migrations.
- `npm run migrate:down` - Reverts the last migration.

## Dependencies

- `pg` - PostgreSQL client for Node.js
- `node-pg-migrate` - Tool for database migrations
- `dotenv` - Management of environment variables
