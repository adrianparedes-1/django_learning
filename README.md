# 📝 Task Manager API (Django + DRF + JWT)

A simple REST API for managing tasks using Django REST Framework and JWT authentication. This project is designed to help developers learn the fundamentals of building secure, token-authenticated APIs using Django.

---

## 🚀 Features

- Full CRUD for Task model via `ModelViewSet`
- JWT Authentication (`djangorestframework-simplejwt`)
- Protected routes using `IsAuthenticated` permission
- Modular structure using DRF routers
- ASGI-ready (can be served with `uvicorn`)
- Django Admin panel for user management

---

## 📦 Installation

1. **Clone the repo**
   ```bash
   git clone https://github.com/your-username/task-manager-api.git
   cd task-manager-api
Create and activate a virtual environment

bash
Copy
Edit
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
Install dependencies

bash
Copy
Edit
pip install -r requirements.txt
Apply migrations

bash
Copy
Edit
python manage.py migrate
Create a superuser

bash
Copy
Edit
python manage.py createsuperuser
Run the server

bash
Copy
Edit
python manage.py runserver
Or use Uvicorn (ASGI server):

bash
Copy
Edit
uvicorn config.asgi:application --reload
🔐 Authentication
This API uses JWT authentication.

🔑 Get Token
POST to /api/token/ with:

json
Copy
Edit
{
  "username": "yourusername",
  "password": "yourpassword"
}
Response:

json
Copy
Edit
{
  "access": "your-access-token",
  "refresh": "your-refresh-token"
}
🔄 Refresh Token
POST to /api/token/refresh/ with:

json
Copy
Edit
{
  "refresh": "your-refresh-token"
}
🔐 Use in Requests
Include the token in your headers:

pgsql
Copy
Edit
Authorization: Bearer <your-access-token>
📁 API Endpoints
Method	Endpoint	Description
GET	/tasks/	List all tasks
POST	/tasks/	Create new task
GET	/tasks/<id>/	Retrieve a task
PUT	/tasks/<id>/	Update a task
DELETE	/tasks/<id>/	Delete a task

All endpoints are protected. You must be authenticated with a valid JWT token.

🛠 Project Structure
bash
Copy
Edit
taskmanager/
├── models.py        # Task model
├── serializers.py   # Task serializer
├── views.py         # ViewSet using ModelViewSet
├── urls.py          # App-level router
config/
├── settings.py      # Project settings incl. REST & JWT config
├── urls.py          # Main routes incl. token endpoints
📚 Tech Stack
Python 3.11+

Django 4.x

Django REST Framework

Simple JWT

Uvicorn (optional, for ASGI)

🧪 Testing Endpoints
Use tools like:

Postman

Insomnia

curl in terminal

DRF Browsable API (with session login)