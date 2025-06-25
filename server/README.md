# Virtual Bookshelf API

This is a REST API for the Virtual Bookshelf application built with ASP.NET Core.

## Prerequisites

- .NET 9.0 SDK or later
- An IDE (Visual Studio, VS Code, or JetBrains Rider)

## Getting Started

1. Clone the repository
2. Navigate to the project directory
3. Run the following commands:

```bash
dotnet restore
dotnet build
dotnet run --project VirtualBookshelf.Api
```

The API will start on:
- **HTTPS**: https://localhost:7117
- **HTTP**: http://localhost:5059

## Database

The application uses SQLite for development, which is automatically created when you run the application for the first time. The database file (`VirtualBookshelf.db`) will be created in the project root.

## API Endpoints

### Books

- `GET /api/books` - Get all books
- `GET /api/books/{id}` - Get a specific book by ID
- `POST /api/books` - Create a new book
- `PUT /api/books/{id}` - Update an existing book
- `DELETE /api/books/{id}` - Delete a book

### Book Model

```json
{
  "id": 1,
  "title": "The Great Gatsby",
  "author": "F. Scott Fitzgerald",
  "isbn": "978-0743273565",
  "description": "A story of the fabulously wealthy Jay Gatsby and his love for the beautiful Daisy Buchanan.",
  "publicationYear": 1925,
  "genre": "Fiction",
  "createdAt": "2025-06-22T03:55:39.767Z",
  "updatedAt": null
}
```

## Project Structure

- `VirtualBookshelf.Api` - Main API project
  - `Controllers/` - API endpoints
  - `Models/` - Data models and DTOs
  - `Services/` - Business logic
  - `Data/` - Data access layer
  - `Middleware/` - Custom middleware components

## Features

- RESTful API endpoints
- Swagger documentation (available at /swagger)
- SQLite database for development
- Entity Framework Core for data access
- Standard HTTP methods (GET, POST, PUT, DELETE)

## Testing the API

You can test the API using:

1. **Swagger UI**: Visit https://localhost:7117/swagger or http://localhost:5059/swagger
2. **curl**: 
   ```bash
   # Get all books
   curl -X GET "https://localhost:7117/api/books"
   
   # Create a new book
   curl -X POST "https://localhost:7117/api/books" \
     -H "Content-Type: application/json" \
     -d '{
       "title": "To Kill a Mockingbird",
       "author": "Harper Lee",
       "isbn": "978-0446310789",
       "description": "A story of racial injustice and the loss of innocence.",
       "publicationYear": 1960,
       "genre": "Fiction"
     }'
   ``` 