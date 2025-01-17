
# Task Management API


## Features

- **Task Management (CRUD):**  
  - Create, Read, Update, and Delete tasks.
  - Tasks include attributes like Title, Description, Due Date, Priority Level, and Status.
  - Validation for due date and status.

- **User Management (CRUD):**  
  - Users can create an account, log in, and manage their tasks.
  - Each user can only access and modify their own tasks.

- **Mark Tasks as Complete or Incomplete:**
  - Users can mark tasks as complete or incomplete.
  - Once marked as complete, tasks cannot be edited unless reverted to incomplete.

- **Task Filters and Sorting:**
  - Filter tasks by status, priority, and due date.
  - Sort tasks by due date or priority.

## Installation

Follow these steps to set up the project locally:

### Prerequisites

- Python 3.x
- Django
- Django REST Framework
- PostgreSQL or SQLite (for database)

### Steps

1. Clone the repository:
   ```bash
   git clone https://github.com/estherdomfeh213/task-manager.git
   cd task-manager
   ```

2. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows, use 'venv\Scripts\activate'
   ```

3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Set up the database:
   - For SQLite (default), you can skip this step.
   - For PostgreSQL, create a database and update the database settings in `project/settings.py`.

5. Apply migrations:
   ```bash
   python manage.py migrate
   ```

6. Create a superuser to access the admin panel (optional):
   ```bash
   python manage.py createsuperuser
   ```

7. Run the development server:
   ```bash
   python manage.py runserver
   ```

   The application will be available at `http://127.0.0.1:8000/`.

### Frontend Setup

The frontend files (HTML, CSS, JS) are located in the `static/` directory. The static files are served by Django in development mode. The frontend interacts with the API through AJAX requests to the backend.

## API Endpoints

### Authentication

- **POST** `/api/auth/login/`:  
  Log in a user and obtain a token for authentication.

- **POST** `/api/auth/signup/`:  
  Register a new user.

### Task Management

- **GET** `/api/tasks/`:  
  Get a list of tasks belonging to the authenticated user.

- **POST** `/api/tasks/`:  
  Create a new task.

- **GET** `/api/tasks/{id}/`:  
  Get details of a specific task.

- **PUT** `/api/tasks/{id}/`:  
  Update a task.

- **DELETE** `/api/tasks/{id}/`:  
  Delete a task.

- **PATCH** `/api/tasks/{id}/complete_task/`:  
  Mark a task as complete.

## Frontend

The frontend is simple and built with HTML, CSS, and JavaScript. The main features include:
- Viewing tasks
- Marking tasks as complete
- Displaying task details

It interacts with the backend API to retrieve and update task data.

### To use the frontend:
1. Open `static/index.html` in a browser to interact with the application.
2. The frontend communicates with the backend using AJAX calls defined in `static/js/script.js`.

## Deployment

You can deploy the application to platforms like **Heroku** or **PythonAnywhere** for the backend. 

To deploy to **Heroku**:

1. Make sure you have Heroku CLI installed.
2. Create a new Heroku app:
   ```bash
   heroku create task-manager-app
   ```
3. Push the code to Heroku:
   ```bash
   git push heroku master
   ```
4. Open the app:
   ```bash
   heroku open
   ```

## Testing

To run the tests:

```bash
python manage.py test
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- [Django](https://www.djangoproject.com/) - Python web framework used for backend development.
- [Django REST Framework](https://www.django-rest-framework.org/) - Toolkit for building Web APIs in Django.
- [Bootstrap](https://getbootstrap.com/) - Frontend framework used for responsive design.
```

---

