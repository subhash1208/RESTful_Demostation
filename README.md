# REST API with Flask

This project contains a REST API built using Flask, a Python web framework. The API allows users to perform CRUD (Create, Read, Update, Delete) operations on a simple database of books.

## Requirements

- Python 3.8 or higher
- The following packages:
  - Flask==2.0.2
  - Flask-SQLAlchemy==2.5.1
  - Flask-Migrate==3.1.0
  - Flask-Cors==3.0.10
  - Flask-Marshmallow==0.14.0
  - marshmallow-sqlalchemy==0.26.1

You can install the required packages using the following command:
``` bash
    pip install -r Requirements.txt
```

## Code

The complete code for the REST API project is included in the `REST.ipynb` Jupyter Notebook.

### Database Setup

The code starts by setting up a simple SQLite database using `Flask-SQLAlchemy`. The database contains a single table called `Books` with the following columns:

* `id`: a unique identifier for each book
* `title`: the title of the book
* `author`: the author of the book
* `year`: the year the book was published

The code also sets up database migrations using `Flask-Migrate`. This allows the database schema to be easily updated as the API evolves.

### Models

The code defines a `Book` model using `Flask-SQLAlchemy`. The `Book` model corresponds to the `Books` table in the database. The code also defines a `BookSchema` class using `marshmallow-sqlalchemy`. The `BookSchema` class is used to serialize and deserialize `Book` objects.

### Routes

The code defines the following routes for the REST API:

* `/books`: a route for retrieving all books in the database
* `/books/<int:book_id>`: a route for retrieving a single book by its ID
* `/books`: a route for creating a new book in the database
* `/books/<int:book_id>`: a route for updating an existing book in the database
* `/books/<int:book_id>`: a route for deleting a book from the database

The code uses the `@app.route` decorator from `Flask` to define the routes. Each route is associated with a function that handles the corresponding HTTP request.

### Serialization and Deserialization

The code uses the `BookSchema` class to serialize and deserialize `Book` objects. The `BookSchema` class is used to convert `Book` objects into JSON format for transmission over the network. The `BookSchema` class is also used to convert incoming JSON data into `Book` objects.

### Error Handling

The code includes error handling for common HTTP errors such as `404 Not Found` and `400 Bad Request`. The code uses the `abort` function from `Flask` to return the appropriate HTTP error code and message.

## Usage

To use the REST API, follow these steps:

1. Run the `REST.ipynb` notebook to start the Flask development server.
2. Use a tool such as `curl` or `Postman` to send HTTP requests to the API.
3. Use the API to perform CRUD operations on the `Books` table in the database.
