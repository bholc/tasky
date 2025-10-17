# Tasky (Go + MongoDB)

> Forked from [jeffthorne/tasky](https://github.com/jeffthorne/tasky)  
> Containerized and documented by **Brock Holcombe**

---

## Overview
Tasky is a lightweight task manager written in **Go (Golang)** using the **Gin** web framework and **MongoDB** for data storage.  
This fork demonstrates end-to-end deployment experience — running locally or inside a Docker container connected to MongoDB.

---

## Tech Stack

| Component | Technology |
|------------|-------------|
| Language   | Go |
| Framework  | Gin |
| Database   | MongoDB |
| Container  | Docker |

---

## Run Locally

```bash
go run main.go

App runs on: http://localhost:8080

Run with Docker (Single Container)

Build and run the app inside a container, connecting to your local MongoDB instance:
docker build -t tasky:latest .
docker run --rm -p 8081:8080 ^
  -e MONGODB_URI="mongodb://host.docker.internal:27017" ^
  -e SECRET_KEY="dev_secret" ^
  tasky:latest

App: http://localhost:8081

MongoDB: running locally (port 27017)

Usage

Open the app and sign up with your email + password.

Log in to view /todo.

Add, mark complete, or delete tasks.

Data persists in MongoDB between restarts.

tasky/
├── controllers/   # API logic
├── models/        # MongoDB schemas
├── assets/        # Static files
├── main.go        # App entry point
├── Dockerfile     # Build instructions
└── README.md

Credit

Original project by Jeff Thorne

Containerization and documentation added by Brock Holcombe
