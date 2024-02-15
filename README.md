# EcommerceApi-JsonServer -  using json-server to create a JSON-based API server for E-commerce Application:

# JSON Server
------> Introduction
json-server is a simple tool that allows you to quickly create a RESTful JSON API server with minimal effort. It's useful for prototyping, mocking APIs, and testing.


# Installation
Install Node.js and npm:
   
    Ensure that you have Node.js and npm installed on your machine. You can download them from https://nodejs.org/.

Install json-server globally:
 Run the following command in your terminal to install json-server globally:

     npm install -g json-server
     
# Getting Started

# create a server.js file:- 

     const PORT = process.env.PORT ||3000
    const jsonServer = require('json-server')
    const server = jsonServer.create()
    const router = jsonServer.router('db.json')
    const middlewares = jsonServer.defaults()
    
    server.use(middlewares)
    server.use(router)
    server.listen(PORT, () => {
      console.log(`JSON Server is running ON ${PORT}`)
    })
    
# Create a db.json file:
Create a db.json file in your project directory. This file will contain your JSON data. For example:


      {
        "posts": [
          { "id": 1, "title": "Hello, JSON Server!" },
          { "id": 2, "title": "Creating a JSON API" }
        ]
      }

      
# Start the json-server:
    Run the following command in your terminal to start the server:

    json-server --watch db.json
    
    This will start a server at http://localhost:3000 with the data from your db.json file.

# Customization

    Changing Port:
    
    By default, the JSON-server uses port 3000. You can specify a different port using the -p option:
   
    json-server --watch db.json -p 4000
    
# Custom Routes:

      Customize routes using the routes option in db.json. For example, map /api/posts to /posts:
      
      {
        "routes": {
          "/api/posts": "/posts"
        },
        "posts": []
      }


# Routes

      List all resources:

      GET /posts
      Get a specific resource:
      GET /posts/1

# Create a new resource:

    POST /posts

# Update a resource:

    PUT /posts/1

# Delete a resource:

    DELETE /posts/1

# Filters
    Filter by property:
    
    GET /posts?title=Hello
    
# Sorting
      Sort by property:

    GET /posts?_sort=title
    
# Pagination

    Limit and offset:
    
    GET /posts?_limit=10&_page=2

# Database Relationships

      Create relationships in db.json:
      
      {
        "posts": [
          { "id": 1, "title": "Post 1", "userId": 1 }
        ],
        "users": [
          { "id": 1, "name": "User 1" }
        ]
      }
Get related resources:
    
    GET /posts/1?_expand=user

# Middleware
    Use custom middleware:
    Create a JavaScript file (e.g., middleware.js) and run json-server with the --middlewares option:
    
    json-server --watch db.json --middlewares middleware.js

# CLI Options

         See all CLI options:
         
         json-server --help

# Contributing
Contributions are welcome! Feel free to open issues or pull requests for any improvements or additional features.


 <h1 align="center" >THANKYOU</h1>
