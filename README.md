# Express.js Product API

This is a RESTful API built using Express.js for managing a list of products. It supports full CRUD operations, middleware for logging and authentication, custom error handling, and advanced features like filtering, search, and pagination.

#  How to Run the Server

# 1. Clone the repository
git clone https://github.com/PLP-MERN-Stack-Development/week-2-express-js-assignment-clipperKE.git
cd express-api

# 2. Install dependencies
npm install express body-parser uuid dotenv

# 3. Set up environment variables
Create a .env file from .env.example:
   cp .env.example .env
Edit .env to include your API key:
   nano .env.example
   PORT=3000
   API_KEY=my-secret-key 
#ctrl o + enter to save
#ctrl x to exit

# 4. Start the server
npm start
Server will run on: http://localhost:3000

# API Endpoints
http://localhost:3000/api/products

# GET /api/products
 # Example:
   GET /api/products?category=electronics&search=laptop&page=1&limit=1
 # Response:
   {
      "total": 2,
      "page": 1,
      "limit": 1,
      "results": [
      {
         "id": "1",
         "name": "Laptop",
         "description": "High-performance laptop with 16GB RAM",
         "price": 1200,
         "category": "electronics",
         "inStock": true
      }
   ]
   }

# GET /api/products/:id
   # Example:
      GET /api/products/1
   # Response;
      {
         "id": "1",
         "name": "Laptop",
         "description": "High-performance laptop with 16GB RAM",
         "price": 1200,
         "category": "electronics",
         "inStock": true
      }

# POST /api/products
   # Example:
      Request headers:
         x-api-key: my-secret-key
      Request Body:
         {
            "name": "Tablet",
            "description": "Android tablet",
            "price": 250,
            "category": "electronics",
            "inStock": true
         }
   # Response:
         {
            "id": "generated-id",
            "name": "Tablet",
            "description": "Android tablet",
            "price": 250,
            "category": "electronics",
            "inStock": true
         }

# PUT /api/products/:id
   # Example:
      PUT /api/products/1
   # Request Body:
      {
         "price": 1000,
         "inStock": false
      }

# DELETE /api/products/:id
   Protected – Requires x-api-key.
   Delete a product by ID.

# Authentication
   x-api-key: my-secret-key
