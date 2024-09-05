## Objective

Build a Task Management API server in Go that uses SQLite as the database. The API should manage tasks and their steps, allowing clients to perform CRUD operations on tasks and steps. This task simulates building the backend for a task management system, where each task has multiple steps and is associated with an author.

## Requirements

### API Endpoints
- Implement the following CRUD endpoints as defined in the OpenAPI spec:
    - `GET /tasks`: Fetch all tasks.
    - `POST /tasks`: Create a new task.
    - `GET /tasks/{taskId}`: Fetch a task by its ID.
    - `PUT /tasks/{taskId}`: Update an existing task by its ID.
    - `DELETE /tasks/{taskId}`: Delete a task by its ID.
    - `GET /tasks/{taskId}/steps`: Fetch all steps for a task.
    - `POST /tasks/{taskId}/steps`: Add a new step to a task.
    - `PUT /tasks/{taskId}/steps/{stepId}`: Update a specific step of a task.
    - `DELETE /tasks/{taskId}/steps/{stepId}`: Delete a step from a task.

### Database (SQLite)
- Use SQLite to store tasks, steps, and authors.
- Create the following tables:
    - Tasks: Store task details (id, name, description, author_id).
    - Steps: Store step details (id, task_id, step, completed).
    - Authors: Store author details (id, first_name, last_name, username).
- Ensure the database schema includes proper relationships between tasks, steps, and authors.

### Data Models
- Define appropriate models in Go for tasks, steps, and authors.
- Use a library like Bun or the standard library `database/sql` to interact with the SQLite database.
- Organize the project using idiomatic Go project structure (e.g., separate directories for models, handlers, and database operations).

### Error Handling & Validation
- Validate inputs for creating and updating tasks (e.g., non-empty task name, valid step data).
- Implement error handling for cases such as:
    - Updating/deleting a task or step that doesn't exist.
    - Attempting to create a task without necessary data.
- Return appropriate HTTP status codes (e.g., 404 for not found, 400 for bad request, 201 for created).

### Routing & Framework
- Use the standard `net/http` package for routing and request handling.
- Set up routes that correspond to the API endpoints, ensuring each endpoint has a clear handler

## Evaluation Criteria

### Code Quality & Structure
- Clear and maintainable code with appropriate modularization.
- Proper use of Go's idioms and project structure.
- Effective use of error handling, clean interfaces, and clear separation of concerns.

### API Functionality
- The ability to create, read, update, and delete tasks and steps with proper validation and error handling.
- Efficient use of SQLite to handle queries and maintain relationships.

### Database Design
- Well-structured schema with proper foreign key relationships between tasks, steps, and authors.
- Efficient querying and data manipulation using Go and SQLite.

### API Documentation
- Clear and concise comments explaining API routes and the purpose of functions.
- Include a brief README.md explaining how to set up and run the project, including dependencies and database migrations.

Good luck, and we look forward to seeing how you build this API!
