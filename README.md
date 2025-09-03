# Hands-On-L3-Installing-Docker-Building-a-Multi-Container-Microservice
Hands-On L3: Installing Docker &amp; Building a Multi-Container Microservice


Execution Steps:

# 1) Install  Docker Desktop

Windows
a. Go to Docker Desktop for Windows.

b. Download Docker Desktop Installer.exe.

c. Run it with default settings.

d. Start Docker Desktop from the Start Menu.

e. If prompted, enable WSL 2 and restart.

macOS
a. Go to Docker Desktop for Mac.

b. Download the installer for your chip type (Apple Silicon or Intel).

c. Open the .dmg file and drag Docker.app into Applications.

d. Open Docker.app and follow security prompts


# 2) PostgreSQL Setup with Docker

a. Pull the PostgreSQL image docker pull postgres

b. Create and start a PostgreSQL instance docker run -d -p 5432:5432 --name postgres1 -e POSTGRES_PASSWORD=pass12345 postgres

c. Open a terminal to the container docker exec -it postgres1 bash

d. Interact with PostgreSQL using psql psql -d postgres -U postgres


# 3) Run the App

a. `docker compose up`

b. Open on http://localhost:8000


# What I learned

I was reminded of the importance of formatting a `compose.yaml` file correct; spaces and indentation matter. 

I also practiced debugging the app.py file, since the imports were wrong initially. `import redis from flask` was changed to `from flask import Flask` and `import Flask app = Flask(__name__)` was changed to `app = Flask(__name__)` and finally all appropriate indentation in app.py was taken care of. 

I was also reminded of the need to use `docker compose up --build` to rebuild a Docker image and start its associated container. This command useful when changes have been made to a Dockerfile or application code, and ensures that running containers use the intended latest version of the image.

