# proyectointermodularrafaymarcos

Project: Library Management System with Docker

This project is a Library Management System developed using Docker to containerize the application. It consists of a backend (PHP with PostgreSQL), a frontend (HTML/CSS/JS with Nginx), and a PostgreSQL database to manage library operations such as book loans, user management, and sanctions. The application is designed to be easily deployable in different environments (development, testing, production) using Docker containers.
Features

    CRUD Operations: Create, Read, Update, and Delete operations for books, users, authors, and loans.

    Dockerized Infrastructure: The application is deployed using Docker containers for the backend, frontend, and database.

    Database Design: A well-structured PostgreSQL database with tables for users, books, authors, loans, and sanctions.

    Backup and Recovery: Automated backup scripts for the frontend, backend, and Docker Compose configuration.

    User-Friendly Interface: A web interface designed following W3C standards with a color scheme that matches the library theme.

    Resource Management: CPU and memory limits are set for Docker containers to prevent excessive resource usage.

Project Structure

/home/rafa/proyectointermodular/
├── backend/                  # Backend code (PHP)
├── frontend/                 # Frontend code (HTML/CSS/JS)
├── backups/                  # Backup files for frontend, backend, and Docker Compose
├── scripts/                  # Backup and cleanup scripts
├── docker-compose.yml        # Docker Compose configuration
└── README.md                 # Project documentation

Docker Containers

The application is divided into three main containers:

    Backend: A PHP container with Apache to handle the application logic.

    Frontend: An Nginx container to serve the static web pages.

    Database: A PostgreSQL container to store all library-related data.

Database Design

The database BIBLIOTECA_DB includes the following tables:

    USUARIOS: Manages user information (name, DNI, email, phone, address, registration date).

    CATEGORIAS: Stores book categories.

    LIBROS: Contains book details (title, category, publisher, publication year, ISBN).

    AUTORES: Stores author information (name, nationality).

    LIBROS_AUTORES: Links books to their authors.

    EJEMPLARES: Manages book copies (internal code, status: Available, Borrowed, Damaged, Lost).

    PRESTAMOS: Tracks book loans (user ID, book copy ID, loan date, return date, returned status).

    SANCIONES: Manages user sanctions (user ID, date, fine amount, paid status).

Database Features

    Function: Calculates the number of days a book return is overdue.

    Stored Procedure: Registers a new loan.

    Trigger: Updates the status of a book copy when it is borrowed or returned.

    Index: Improves the search for books by title.

    View: Displays books with their authors and availability.

Backup and Recovery

Automated backup scripts are configured to ensure data safety:

    Frontend Backup: Compresses the frontend directory into a .tar.gz file.

    Backend Backup: Compresses the backend directory into a .tar.gz file.

    Docker Compose Backup: Creates a copy of the docker-compose.yml file.

    Cleanup Script: Deletes backups older than 30 days to manage storage space.

Deployment

Prerequisites

    Docker installed.

    Docker Compose installed.

Steps to Deploy

    Clone the repository:

    git clone https://github.com/your-username/proyectointermodular.git
    cd proyectointermodular

    Start the application using Docker Compose:

    docker-compose up --build

    Access the application:

        Frontend: Open http://localhost:8080 in your browser.

        Backend: Access http://localhost:8081 for the API.

        Database: Connect to PostgreSQL at localhost:5434.

Resource Management

To prevent excessive resource usage, CPU and memory limits are set for the Docker containers in the docker-compose.yml file.
Documentation

    User Guide: Explains how to install, configure, and use the application.

    Technical Documentation: Describes the project structure, database design, and deployment process.

    README.md: Provides a summary of the project in both Spanish and English.

Docker Hub

The project uses Docker Hub to store and manage Docker images. A user account has been created for the team to publish and share images.
