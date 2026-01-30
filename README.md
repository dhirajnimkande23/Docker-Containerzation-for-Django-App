# Docker-Containerzation-for-Django-App
This project demonstrates how to containerize a Django web application using Docker for easy deployment and consistent environments.

📦 Tech Stack

Python 3

Django

Docker

Ubuntu / Python Slim Image

📁 Project Structure
.
├── Dockerfile
├── requirements.txt
└── devops/
    ├── manage.py
    ├── project/
    └── app/

🚀 Getting Started
✅ Prerequisites

Make sure you have:

Docker installed

Git (optional)

Check:

docker --version

🛠 Build Docker Image
docker build -t django-image .

▶ Run Django Container
docker run -p 8000:8000 django-image

🌐 Access the App

Open in browser:

http://localhost:8000


(or EC2 public IP if running on server)

📄 Sample Dockerfile (Optimized)
FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt

COPY devops/ .

EXPOSE 8000

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]

📌 Why Use Docker?

✅ Consistent environment
✅ Easy deployment
✅ No “works on my machine” issues
✅ CI/CD ready

🧠 Common Issues & Fixes
Port not accessible?

Make sure you use:

-p 8000:8000

Django not loading?

Ensure:

ALLOWED_HOSTS = ['*']


(in development only)

📈 Future Improvements

Add Gunicorn for production

Add Nginx reverse proxy

Use docker-compose with PostgreSQL

Add environment variables

👨‍💻 Author

Dhiraj Nimkande
Cloud & DevOps Engineer
