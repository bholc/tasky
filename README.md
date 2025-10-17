Tasky (Go + MongoDB)

Forked from jeffthorne/tasky
.

Overview

Tasky is a simple task manager written in Go (Gin framework) that uses MongoDB for persistence.
This fork demonstrates both local development and containerized deployment experience using Docker.

How to Run (Local)
go run main.go


App runs on: http://localhost:8080

How to Run (Dockerfile, single container)

Build and run the app inside a container while connecting to your local MongoDB host:

docker build -t tasky:latest .
docker run --rm -p 8081:8080 ^
  -e MONGODB_URI="mongodb://host.docker.internal:27017" ^
  -e SECRET_KEY="dev_secret" ^
  tasky:latest


App runs on: http://localhost:8081

MongoDB runs locally (Community Server on port 27017).

Environment Variables
MONGODB_URI=mongodb://localhost:27017
SECRET_KEY=dev_secret

Usage

Open the app in your browser.

Sign up with an email and password.

Log in and add tasks at /todo.

Data persists in MongoDB between app restarts.

Credit

Original project by Jeff Thorne
.
Containerization and documentation added by Brock Holcombe.
