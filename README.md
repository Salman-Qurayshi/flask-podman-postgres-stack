# Flask Microservice Lab (Podman + PostgreSQL)

This project demonstrates a secure, containerized Flask microservice with a PostgreSQL backend using Podman and Podman Compose.

## Features
- Flask app containerized with Podman
- PostgreSQL database with persistent volume
- Secure secret handling with Podman secrets
- Multi-container orchestration via Podman Compose
- Image scanning & signing

## Usage

```
git clone https://github.com/your-username/flask-podman-compose

cd flask-microservice-lab

python3 -m venv venv
source venv/bin/activate
pip install flask psycopg2-binary

pip freeze > requirements.txt


podman build -t flask-app .


echo "YourSecret" > db_password.txt
podman secret create db_password db_password.txt



podman-compose up -d

curl http://localhost:5000

curl http://localhost:5000/data

