

## Features

- User registration and authentication.
- CRUD operations for tasks (Create, Read, Update, Delete).
- Real-time updates for task status changes using WebSocket.
- OAuth2 authentication for API access.
- Simple and straightforward project structure.

## Project Structure

The project follows the following directory structure:

```
task_manager_fastapi/
├── app/
│   ├── alembic/
│   ├── api/
│   │   ├── endpoints/
│   │   ├── middleware/
│   │   ├── models/
│   ├── core/
│   ├── db/
├── tests/
├── .env
├── .gitignore
├── alembic.ini
├── README.md
├── main.py
├── requirements.txt
```

- `app`: Contains the main application code.
  - `alembic`: Database migration files (if used).
  - `api`: Contains API endpoints for tasks and users.
    - `endpoints`: Task and user API endpoints.
    - `middleware`: Custom middleware (simple logging for example).
    - `models`: Pydantic models for request and response.
  - `core`: Core utilities and configurations.
  - `db`: Database configuration and models.
- `tests`: Unit tests.
- `.env`: Store environment variables (e.g., database credentials).
- `.gitignore`: Lists files and directories to be ignored by version control.
- `alembic.ini`: Alembic configuration (if used).
- `README.md`: Documentation about the project.
- `requirements.txt`: List of project dependencies.

## Getting Started

### Prerequisites

Before running the application, make sure you have the following prerequisites installed:

- Python 3.7+ (3.10+ recommended).
- PostgreSQL.

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/Cheater121/task_manager_fastapi.git
   cd task_manager_fastapi
   ```

2. Create a virtual environment (recommended):

   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows, use venv\Scripts\activate.bat
   ```

3. Install project dependencies:

   ```bash
   pip install -r requirements.txt
   ```

## Usage

### Running the Application

To run the FastAPI application locally, use the following command:

```bash
uvicorn main:app --host 0.0.0.0 --port 8000 --reload
```

Replace `0.0.0.0` and `8000` with your desired host and port.

Or you can just run `main.py`:
```bash
python3 main.py
```

### API Endpoints

The API exposes the following endpoints:

- `POST /api/v1/users/register/`: Register a new user.
- `POST /api/v1/users/login/`: Authenticate and receive a JWT token.
- `GET /api/v1/about_me/`: Retrieve user info (protected endpoint).
- `GET /api/v1/tasks/`: Retrieve a list of tasks (protected endpoint).
- `POST /api/v1/tasks/`: Create a new task (protected endpoint).
- `GET /api/v1/tasks/{task_id}`: Retrieve a specific task (protected endpoint). 
- `PUT /api/v1/tasks/{task_id}`: Update a specific task (protected endpoint).
- `DELETE /api/v1/tasks/{task_id}`: Delete a specific task (protected endpoint). 

For real-time updates on task status changes, use WebSocket connections to `/ws/tasks/{client_id}`.


## Testing the API with Swagger UI

Fast API comes with Swagger UI. This tool is automatically generated based on your API's route definitions and Pydantic models.

### Accessing Swagger UI

Once the API is running, Swagger UI can be accessed on the following URL:

```bash
http://localhost:8000/docs
```

You can use swagger UI to:

1. **Browse Endpoints**
2. **Send Requests**
3. **View Responses**
4. **Test Validations**

**To Test with SwaggerUI, you can do the following for each endpoint explained above**

1. Open your web browser and navigate to the /docs path as mentioned above.

2. Explore the available endpoints and select the one you want to test.

3. Click on the "Try it out" button to open an interactive form where you can input data.

4. Fill in the required parameters and request body (if applicable) according to the API documentation given above.

5. Click the "Execute" button to send the request to the API.

6. The response will be displayed below, showing the status code and response data.

7. You can also view example request and response payloads, which can be helpful for understanding the expected data format.

## Testing the API with pytest Framework

A suite of `tests` using the pytest framework was used to help verify the functionality of the Task Manager FastAPI.

### Running the tests

1. Navigate to the `task_manager_fastapi` (root) directory using a terminal:

```bash
cd <your_path_to_project>/task_manager_fastapi
```

2. Run the tests by executing the following command (don't forget to activate your virtual environment if used):

```bash
pytest
```



