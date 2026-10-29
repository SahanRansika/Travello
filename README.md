
# Travello – Travel Booking System

A web-based travel booking system designed to help users explore travel destinations, view hotels and transportation options, and submit travel booking requests. The system also provides an admin interface to manage travel catalogue information and monitor booking requests.
<img width="1700" height="1100" alt="Travello drawio (1)" src="https://github.com/user-attachments/assets/664142bf-75d4-49fb-ad11-d0b2ed59c743" />
## Table of Contents

- [About the Project](#about-the-project)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Backend Setup](#backend-setup)
- [Frontend Setup](#frontend-setup)
- [Running the Application](#running-the-application)
- [Admin Access](#admin-access)
- [API Overview](#api-overview)
- [Configuration](#configuration)
- [Troubleshooting](#troubleshooting)
- [Future Improvements](#future-improvements)
- [Author](#author)

## About the Project

Travello is a travel booking web application developed to provide a convenient way to explore travel-related services through a simple web interface.

The application consists of two main parts:

- **Backend:** A RESTful API developed using Java and Spring Boot, responsible for authentication, catalogue management, and travel booking requests.
- **Frontend:** A lightweight web interface built using HTML, CSS, and JavaScript, containing a public booking page and an admin management page.

The backend uses a layered architecture with controllers, services, repositories, models, DTOs, and security components to keep the application organized and maintainable.

## Features

### Public Website

- Browse available travel destinations.
- View hotel information, descriptions, images, and prices.
- Explore available transportation options.
- Submit travel booking requests.
- Access public travel catalogue information.
- Interact with the backend REST API.

### Admin Panel

- Authenticate administrators securely.
- Manage travel catalogue information.
- Add, update, and delete catalogue records where supported.
- Manage destinations, hotels, and transportation options.
- View an overview of the system.
- Review and manage travel requests where supported.

### Backend

- RESTful API architecture.
- User authentication and authorization.
- JWT-based authentication support.
- Role-based access control.
- Spring Data repositories.
- Centralized exception handling.
- Initial administrator configuration.
- Catalogue and travel request management.

## Technologies Used

### Backend

- Java
- Spring Boot
- Spring Web
- Spring Security
- Spring Data JPA or the configured persistence technology
- JSON Web Token (JWT)
- Maven
- Database configured for the project

> Note: Confirm the actual database dependency and persistence configuration in the backend before choosing the final database description.

### Frontend

- HTML5
- CSS3
- JavaScript
- Fetch API for backend communication

### Development Tools

- Git
- GitHub
- IntelliJ IDEA or another Java IDE
- Visual Studio Code
- Postman

## Project Structure

The repository is organized into separate frontend and backend directories.

```text
Travello/
│
├── Backend/
│   ├── src/
│   │   └── main/
│   │       ├── java/
│   │       │   └── lk/
│   │       │       └── travello/
│   │       │           ├── TravelloApplication.java
│   │       │           │
│   │       │           ├── controller/
│   │       │           │   ├── AuthController.java
│   │       │           │   ├── PublicController.java
│   │       │           │   ├── AdminCatalogueController.java
│   │       │           │   ├── AdminOverviewController.java
│   │       │           │   └── TravelRequestController.java
│   │       │           │
│   │       │           ├── service/
│   │       │           │   ├── AuthService.java
│   │       │           │   ├── CatalogueService.java
│   │       │           │   ├── TravelRequestService.java
│   │       │           │   └── impl/
│   │       │           │       ├── AuthServiceImpl.java
│   │       │           │       ├── CatalogueServiceImpl.java
│   │       │           │       └── TravelRequestServiceImpl.java
│   │       │           │
│   │       │           ├── model/
│   │       │           │   ├── AppUser.java
│   │       │           │   ├── Role.java
│   │       │           │   ├── Destination.java
│   │       │           │   ├── Hotel.java
│   │       │           │   ├── TransportOption.java
│   │       │           │   ├── CatalogueStatus.java
│   │       │           │   ├── TravelRequest.java
│   │       │           │   └── RequestStatus.java
│   │       │           │
│   │       │           ├── repository/
│   │       │           │   ├── AppUserRepository.java
│   │       │           │   ├── DestinationRepository.java
│   │       │           │   ├── HotelRepository.java
│   │       │           │   ├── TransportOptionRepository.java
│   │       │           │   └── TravelRequestRepository.java
│   │       │           │
│   │       │           ├── config/
│   │       │           │   ├── SecurityConfig.java
│   │       │           │   └── BootstrapAdminConfig.java
│   │       │           │
│   │       │           ├── security/
│   │       │           │   ├── JwtService.java
│   │       │           │   ├── JwtAuthenticationFilter.java
│   │       │           │   └── CustomUserDetailsService.java
│   │       │           │
│   │       │           ├── dto/
│   │       │           │   ├── AuthDtos.java
│   │       │           │   ├── CatalogueDtos.java
│   │       │           │   └── TravelRequestDtos.java
│   │       │           │
│   │       │           └── exception/
│   │       │               ├── ResourceNotFoundException.java
│   │       │               └── ApiExceptionHandler.java
│   │       │
│   │       └── resources/
│   │           └── application.properties
│   │
│   └── pom.xml
│
├── Frontend/
│   ├── index.html
│   └── admin.html
│
└── README.md
```

> The directory names `Backend` and `Frontend` are examples. Use the actual directory names in your GitHub repository. The backend structure also assumes that `pom.xml` and `application.properties` are present.

## Prerequisites

Install the following software before running the application:

- Java JDK compatible with the version specified in the backend project.
- Apache Maven, or use the Maven Wrapper if the project includes one.
- The database configured in the backend.
- Git.
- A modern web browser.
- Visual Studio Code or another editor for the frontend.

Check the installed versions:

```bash
java -version
mvn -version
git --version
```

## Getting Started

### 1. Clone the Repository

Open a terminal and execute:

```bash
git clone https://github.com/SahanRansika/Travello.git
```

Navigate to the project directory:

```bash
cd Travello
```

If the repository is private, make sure you have the required GitHub access.

### 2. Check the Project Files

```text
Travello/
├── Backend/
├── Frontend/
└── README.md
```

Your actual directory names may differ. Navigate into the directories that exist in your repository.

## Backend Setup

### 1. Navigate to the Backend

```bash
cd Backend
```

Make sure the directory contains `pom.xml`.

### 2. Configure the Database

Open:

```text
src/main/resources/application.properties
```

Configure the database connection and other required application properties according to the dependencies and configuration used by your project.

For example, a Spring Boot application using MySQL might require settings such as:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/travello
spring.datasource.username=${DB_USERNAME}
spring.datasource.password=${DB_PASSWORD}
```

**Important:** This is only an example for a MySQL-based application. Do not copy these settings blindly if the existing project uses a different database. Keep your actual database configuration and required JWT settings.

Set environment variables for credentials rather than committing passwords or signing secrets to GitHub.

### 3. Build the Backend

Run:

```bash
mvn clean install
```

To build without running tests:

```bash
mvn clean package -DskipTests
```

### 4. Start the Backend

Run the application using Maven:

```bash
mvn spring-boot:run
```

Alternatively, run the main class:

```text
lk.travello.TravelloApplication
```

If the application uses the default Spring Boot port, the backend will usually be available at:

```text
http://localhost:8080
```

The actual port depends on the application's configuration.

## Frontend Setup

The frontend contains two HTML files:

```text
Frontend/
├── index.html
└── admin.html
```

No separate frontend build command is required for a plain HTML, CSS, and JavaScript application.

### Option 1: Run Using Visual Studio Code

1. Open the `Frontend` folder in Visual Studio Code.
2. Install the Live Server extension if it is not already installed.
3. Right-click `index.html`.
4. Select **Open with Live Server**.
5. Open `admin.html` separately when you need the admin panel.

Live Server usually starts at an address similar to:

```text
http://127.0.0.1:5500/index.html
```

The exact port may differ.

### Option 2: Run Using Python

If Python is installed, navigate to the frontend directory:

```bash
cd Frontend
```

Start a local HTTP server:

```bash
python -m http.server 5500
```

Open the public website:

```text
http://localhost:5500/index.html
```

Open the admin panel:

```text
http://localhost:5500/admin.html
```

Keep the terminal running while using the website.

> Opening the HTML files through a local web server is recommended. The frontend must also be configured to call the correct backend API URL.

## Running the Application

Start the backend and frontend separately.

| Component | Command / Action | Example URL |
|---|---|---|
| Backend | `mvn spring-boot:run` | `http://localhost:8080` |
| Public website | Open `index.html` through Live Server | `http://127.0.0.1:5500/index.html` |
| Admin panel | Open `admin.html` through Live Server | `http://127.0.0.1:5500/admin.html` |

The backend must be running for frontend operations that depend on the API.

If the frontend and backend use different origins, configure Spring Security CORS settings to allow the frontend's actual local origin. Do not disable security globally to fix CORS errors.

## Admin Access

The backend contains the following administrator-related configuration:

```text
config/
├── SecurityConfig.java
└── BootstrapAdminConfig.java
```

`BootstrapAdminConfig.java` may be responsible for initializing an administrator account when the application starts, depending on its implementation.

To access the admin panel:

1. Start the backend.
2. Open `admin.html`.
3. Sign in using the administrator credentials configured for your environment.
4. Use the available catalogue and overview features.

**Security:** Do not publish real administrator passwords, JWT secrets, or production credentials in this repository. Use the credentials and initialization logic defined by the actual backend implementation.

## API Overview

The backend is organized around the following controller classes:

| Controller | Responsibility |
|---|---|
| `AuthController` | Authentication-related operations |
| `PublicController` | Public catalogue and other public operations |
| `AdminCatalogueController` | Administrative catalogue management |
| `AdminOverviewController` | Administrative overview information |
| `TravelRequestController` | Travel request operations |

These responsibilities are based on the class names. Refer to the actual controller mappings and methods to determine the exact API routes, HTTP methods, request bodies, and response formats.

Example REST API URL format:

```text
http://localhost:8080/api/...
```

The `/api` prefix is only an example. The actual base path depends on the controller mappings in the source code.

## Configuration

Before sharing or deploying the project, verify the following:

- Database URL and credentials.
- JWT signing secret and token expiration settings.
- Server port.
- Frontend API base URL.
- CORS allowed origins.
- Initial administrator configuration.
- Any image hosting or external service credentials used by the project.

Use environment variables or a suitable secret-management solution for sensitive values.

Do not commit `.env` files, real passwords, production signing secrets, or private credentials.

## Troubleshooting

### Backend Does Not Start

Check your Java and Maven versions:

```bash
java -version
mvn -version
```

Confirm that the configured database is running and the database credentials are correct.

### Frontend Cannot Connect to Backend

- Confirm that the backend is running.
- Check the API base URL used in `index.html` and `admin.html`.
- Inspect the browser developer console and Network tab.
- Verify the CORS configuration.
- Confirm that the requested endpoint exists in the backend.

### Admin Login Fails

- Check the configured administrator account.
- Verify the authentication endpoint and request payload.
- Confirm that the JWT configuration is valid.
- Check the backend logs for authentication errors.

### Maven Build Fails

Run:

```bash
mvn clean install
```

Review the first meaningful compilation or dependency error in the terminal output.

## Future Improvements

- Online payment integration.
- Booking confirmation notifications.
- Advanced search and filtering.
- User booking history.
- Responsive UI improvements.
- Automated unit and integration testing.
- Deployment with production environment configuration.

## Author

**Sahan Ransika Kumara**

- GitHub: [SahanRansika](https://github.com/SahanRansika)

## License

Add a suitable open-source license to the repository if you intend to distribute or reuse this project publicly.
