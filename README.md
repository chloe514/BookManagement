Brief Report
Design Choices:
The project follows a layered architecture, which separates concerns into distinct layers: the Controller, Service, Repository, and Model. This approach promotes code organization, reusability, and maintainability. The BookController handles HTTP requests and responses, delegating the business logic to the BookService. The BookService interacts with the BookRepository to perform CRUD operations on the Book entity. This separation of responsibilities ensures that each layer focuses on a specific aspect of the application, making the codebase easier to understand and modify in the future.

Challenges and Solutions:
One challenge encountered was missing getters and setters in the Book entity, which caused errors when accessing and modifying the book attributes in the BookService. This was resolved by generating the necessary getters and setters in the Book class using IntelliJ's built-in generator. Another challenge was correctly organizing the project structure to ensure all classes were in the appropriate packages. This was addressed by using IntelliJ’s refactoring tools to move and organize classes into the correct sub-packages (controller, service, repository, and model), ensuring a clean and maintainable project layout.

Sample Requests:
Here are some sample requests and their expected responses:

GET /api/books:

Request: Retrieve all books.
Expected Response: [] (empty array if no books) or a list of book objects.
POST /api/books:

Request:
{
"title": "Test Book",
"author": "John Doe",
"publicationYear": 2024
}
Expected Response:
{
"id": 1,
"title": "Test Book",
"author": "John Doe",
"publicationYear": 2024
}
GET /api/books/1:

Request: Retrieve the book with ID 1.
Expected Response:
{
"id": 1,
"title": "Test Book",
"author": "John Doe",
"publicationYear": 2024
}

PUT /api/books/1:
Request:
{
"title": "Updated Book Title",
"author": "Jane Doe",
"publicationYear": 2025
}
Expected Response:
{
"id": 1,
"title": "Updated Book Title",
"author": "Jane Doe",
"publicationYear": 2025
}
DELETE /api/books/1:

Request: Delete the book with ID 1.
Expected Response: No content (HTTP Status 204).
This approach ensures that the application is well-structured, with clear separation of responsibilities and easily testable endpoints.









