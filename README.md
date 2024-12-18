# Restaurant Menu API

API to provide data to a restaurant menu application. This API should use nodeJS and GraphGL


## Features

- GraphQL API with Query and Mutation support

- Sequelize ORM for database management

- MySQL as the database backend

- Migrations and seed data

- Jest for unit testing

- Supertest for API testing


## Prerequisites

Before starting, ensure you have the following installed:

- Node.js (v14 or higher)

- npm or yarn

- MySQL


## Setup Instructions

1. Clone the Repository

  ```bash
  $ git clone <repository_url>
  $ cd restaurant-menu-api
  ```

2. Install Dependencies

  ```
  npm install
  ```

3. Configure the Database

Edit the config/config.json file to set up your MySQL database credentials:

4. Run Migrations and Seed Data

  ```bash
  $ npx sequelize-cli db:migrate
  $ npx sequelize-cli db:seed:all
  ```

5. Start the Server

  ```
  npm start
  ```

The server will start at http://localhost:4000/graphql.


## GraphQL API Endpoints

### Queries

- Fetch All Menus

  ```bash
  query {
    menus {
      id
      name
      type
      price
    }
  }
  ```

- Fetch a Menu by ID

  ```bash
  query {
    menu(id: 1) {
      id
      name
      type
      price
    }
  }
  ```

### Mutations

- Add a New Menu

  ```bash
  mutation {
    addMenu(name: "Iceberg Wedge Salad with House Cured Bacon – tomato salsa gorgonzola", type: "appetizers", price: 7.5) {
      id
      name
      type
      price
    }
  }
  ```

- Update a Menu

  ```bash
  mutation {
    updateMenu(id: 1, name: "Iceberg Wedge Salad with House Cured Bacon – tomato salsa gorgonzola", type: "appetizers", price: 7.5) {
      id
      name
      type
      price
    }
  }
  ```

- Delete a Menu

  ```bash
  mutation {
    deleteMenu(id: 1) {
      id
    }
  }
  ```


## Testing

Run Tests

Jest is used for unit testing, and Supertest is used for API testing.

```
npm test
```