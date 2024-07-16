# Task List API

This repository contains the backend code for a Task List application built with Laravel. Follow the steps below to clone the repository, set up the environment, and run the application.

## Prerequisites

Before you begin, ensure you have the following installed on your local machine:

- PHP >= 7.3
- Composer
- MySQL (or any other database supported by Laravel)
- Node.js & npm (for frontend assets and tools)

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/task-list-api.git
cd task-list-api

### 2. Install PHP dependencies using Composer:

composer install

###3 Copy the example environment file and update the configuration:

cp .env.example .env

### 4. Generate an application key:

php artisan key:generate


### 5. Configure the Database Update the .env file with your database configuration:

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=your_database_name
DB_USERNAME=your_database_username
DB_PASSWORD=your_database_password


### 6. Run the database migrations to set up the database schema:

php artisan migrate

### 7. Seed the Database

php artisan db:seed


### 8. Start the local development server:

php artisan serve


### 9. The main endpoint for this application is:

http://localhost:8000/api/v1/tasks/

keep in mind that the port number 8000 might differ in your local machine. you would be able to see this when you start the local development server.

### 10. CRUD endpoints

it is possible to see all api endpoints by sending the following in terminal 

php artisan route:list

endpoint to show all existing tasks

    http://localhost:8000/api/v1/tasks

endpoint to show a specific task by id: keep note that the /11 indicates passing 11 as an id. if there are no tasks with id 11 it should return null.

    http://localhost:8000/api/v1/tasks/11

endpoint to create task: this also includes sending the task information in a json format as seen below 

    http://localhost:8000/api/v1/tasks

    {
    "name": "Task Hand",
    "priority_id": 2
    }   


endpoint to update task: this should also be sent with json format body with information to be updated like below

    http://localhost:8000/api/v1/tasks/11

    {
        "name": "Task one updated"
    }

endpoint to delete a task: this includes the id of the task

    http://localhost:8000/api/v1/tasks/11