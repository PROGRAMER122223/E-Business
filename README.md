# E-Business

## Description

It is a  back end for an e-commerce site   configuring  a working Express.js API to use Sequelize to interact with a MySQL database.

## User Story

```md
AS A manager at an internet retail company
I WANT a back end for my e-commerce website that uses the latest technologies
SO THAT my company can compete with other e-commerce companies
```
## Acceptance Criteria

```md
GIVEN a functional Express.js API
WHEN I add my database name, MySQL username, and MySQL password to an environment variable file
THEN I am able to connect to a database using Sequelize
WHEN I enter schema and seed commands
THEN a development database is created and is seeded with test data
WHEN I enter the command to invoke the application
THEN my server is started and the Sequelize models are synced to the MySQL database
WHEN I open API GET routes in Insomnia for categories, products, or tags
THEN the data for each of these routes is displayed in a formatted JSON
WHEN I test API POST, PUT, and DELETE routes in Insomnia
THEN I am able to successfully create, update, and delete data in my database
```
## Mock-Up

The following animation shows the application's GET routes to return all categories, all products, and all tags being tested in Insomnia:

[In Insomnia, the user tests “GET tags,” “GET Categories,” and “GET All Products.”.](https://watch.screencastify.com/v/DN0wKcNRJLD92BDUvyId)

The following animation shows the application's GET routes to return a single category, a single product, and a single tag being tested in Insomnia:

[In Insomnia, the user tests “GET tag by id,” “GET Category by ID,” and “GET One Product.”](https://watch.screencastify.com/v/HpQcBDjbqVkxUBR0M1xW)

The following animation shows the application's POST, PUT, and DELETE routes for categories being tested in Insomnia:

[In Insomnia, the user tests “DELETE Category by ID,” “CREATE Category,” and “UPDATE Category.”](https://watch.screencastify.com/v/AeL7nIphABnsm42rPoth)


## Getting Started
 1.Import [MySQL2](https://www.npmjs.com/package/mysql2) and [Sequelize](https://www.npmjs.com/package/sequelize) packages to connect Express.js API to a MySQL database.
 2.Import [dotenv](https://www.npmjs.com/package/dotenv) package to use environment variables to store sensitive data.

Use the `schema.sql` file in the `db` folder to create your database with MySQL shell commands. Use environment variables to store sensitive data like your MySQL username, password, and database name.
  
### Database Models

Database should contain the following four models, including the requirements listed for each model:

* `Category`

  * `id`

    * Integer.
  
    * Doesn't allow null values.
  
    * Set as primary key.
  
    * Uses auto increment.

  * `category_name`
  
    * String.
  
    * Doesn't allow null values.

* `Product`

  * `id`
  
    * Integer.
  
    * Doesn't allow null values.
  
    * Set as primary key.
  
    * Uses auto increment.

  * `product_name`
  
    * String.
  
    * Doesn't allow null values.

  * `price`
  
    * Decimal.
  
    * Doesn't allow null values.
  
    * Validates that the value is a decimal.

  * `stock`
  
    * Integer.
  
    * Doesn't allow null values.
  
    * Set a default value of `10`.
  
    * Validates that the value is numeric.

  * `category_id`
  
    * Integer.
  
    * References the `Category` model's `id`.

* `Tag`

  * `id`
  
    * Integer.
  
    * Doesn't allow null values.
  
    * Set as primary key.
  
    * Uses auto increment.

  * `tag_name`
  
    * String.

* `ProductTag`

  * `id`

    * Integer.

    * Doesn't allow null values.

    * Set as primary key.

    * Uses auto increment.

  * `product_id`

    * Integer.

    * References the `Product` model's `id`.

  * `tag_id`

    * Integer.

    * References the `Tag` model's `id`.

### Associations

* `Product` belongs to `Category`, and `Category` has many `Product` models, as a category can have multiple products but a product can only belong to one category.

* `Product` belongs to many `Tag` models, and `Tag` belongs to many `Product` models. Allow products to have multiple tags and tags to have many products by using the `ProductTag` through model.


### Seed the Database

After creating the models and routes, run `npm run seed` to seed data to your database so that you can test your routes.

### Sync Sequelize to the Database on Server Start

Create the code needed in `server.js` to sync the Sequelize models to the MySQL database on server start.


## Walkthrough video



## URL
Github link to E-Business [https://github.com/PROGRAMER122223/E-Business]
## Walkthrough video
1.(getRoute for all)[https://watch.screencastify.com/v/DN0wKcNRJLD92BDUvyId]
2.(getbyId)[https://watch.screencastify.com/v/HpQcBDjbqVkxUBR0M1xW]
3.(CRUD on categories)[https://watch.screencastify.com/v/AeL7nIphABnsm42rPoth]
4.(CRUD on products)[https://watch.screencastify.com/v/S2xr5MVw175sUvHbYxqJ] 
5.(CRUD on Tags)[https://watch.screencastify.com/v/6vjS9tXzF0I3pnocEfNQ]