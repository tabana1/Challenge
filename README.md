# Challenge

## Overview
## Tech Stack

- PHP (Laravel)
- Nuxt.js
- Nginx
- MySQL
- Docker
- GitHub Actions for CI/CD



This repository contains a simple web application with two main components:

1. **API**: Written in Laravel PHP, the API serves as the backend for the application and listens on port 8000.
2. **Client**: Developed using Nuxt.js, the client is the frontend of the application and listens on port 3000.

## Installation

1. ### Clone the repository:

   ```bash
   git clone https://github.com/tabana1/Challenge.git
   cd Challenge 

2. ### Environment Variables

- **API Directory**: Take a look at the `.env` file in the API directory. It should contain the necessary credentials to connect to the database.

  ```env
    DB_CONNECTION=mysql
    DB_HOST=db
    DB_PORT=3306
    DB_DATABASE=bookapi
    DB_USERNAME=app
    DB_PASSWORD=password
  ```

- **Client Directory**: Check the `.env` file in the Client directory. It should contain the connection string to connect to the API.

  ```env
    VITE_API_URL=http://api:8000
  ```
3. ### Set up Docker containers:
   ```bash
    docker-compose up --build
   ```
4. ### Access the services:

   Laravel API: http://localhost:8000

   Nuxt.js client: http://localhost:3000
 
5. ### CI/CD Workflow
     
    - Pushes to the ```main``` branch trigger GitHub Actions to build and push Docker images to Docker Hub.
    - Add Docker Hub credentials as GitHub secrets:``` DOCKER_HUB_USERNAME``` and ```DOCKER_HUB_PASSWORD```.
