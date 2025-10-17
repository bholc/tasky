Tasky (Go and MongoDB)

Forked from https://github.com/jeffthorne/tasky

Containerization and documentation by Brock Holcombe.

Overview
Tasky is a lightweight task manager written in Go using the Gin framework and MongoDB for storage.
This fork demonstrates how to run the app locally and inside a Docker container that connects to a MongoDB instance.

How to run locally

1. Open a terminal in the project folder.
2. Run the following command:
go run main.go
3. Open your browser and go to http://localhost:8080

How to run with Docker

1. Build the image:
docker build -t tasky:latest .
2. Run the container, connecting it to MongoDB on your computer:
docker run --rm -p 8081:8080 -e MONGODB_URI="mongodb://host.docker.internal:27017" -e SECRET_KEY="dev_secret" tasky:latest
3. Open your browser and go to http://localhost:8081

Environment variables
MONGODB_URI = mongodb://localhost:27017
SECRET_KEY = dev_secret

Usage

1. Open the app in your browser.
2. Sign up with an email and password.
3. Log in and go to /todo to add, complete, or delete tasks.
4. Data is stored in MongoDB and persists after restarting the app.

Project structure
controllers - API logic
models - MongoDB data models
assets - Static files
main.go - Application entry point
Dockerfile - Build instructions
README.md - Documentation

Credit
Original project by Jeff Thorne (https://github.com/jeffthorne/tasky
)
This fork documents and demonstrates containerized usage by Brock Holcombe.
