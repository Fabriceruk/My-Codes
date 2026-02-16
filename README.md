# Servlet Assignments

A Maven-based Java web application demonstrating servlet functionality using Apache Tomcat. This project includes two servlets: one for handling login requests and another for redirecting users to Google search results.

## Project Structure

```
servlet-assignments/
├── src/
│   ├── main/
│   │   ├── java/com/example/
│   │   │   ├── LoginServlet.java      # Handles POST requests for login
│   │   │   └── RedirectServlet.java   # Handles GET requests for search redirect
│   │   └── webapp/
│   │       ├── index.html             # Home page with links
│   │       ├── login.html             # Login form
│   │       ├── redirect.html          # Search form
│   └── test/
├── pom.xml                             # Maven configuration
└── target/                             # Build output
```

## Overview

### LoginServlet
- **URL Path**: `/login`
- **Method**: POST
- **Purpose**: Validates username and password, displays login result
- **Form**: `login.html`

### RedirectServlet
- **URL Path**: `/redirect`
- **Method**: GET
- **Purpose**: Redirects user to Google search with the provided query
- **Form**: `redirect.html` (Search form with "Fetch" button)

## Prerequisites

- **Java**: JDK 8 or higher
- **Maven**: 3.6 or higher
- **Tomcat 7**: (Included via Maven plugin)

## Building the Project

```bash
cd d:\My_Pjoject\Servlet\My-Codes-main
mvn clean compile
```

## Running the Application

1. Start Tomcat using Maven:
   ```bash
   mvn tomcat7:run
   ```

2. Access the application in your browser:
   ```
   http://localhost:8080/
   ```

## Available URLs

| URL | Purpose |
|-----|---------|
| `http://localhost:8080/` | Home page with links to both forms |
| `http://localhost:8080/login.html` | Login form (username & password) |
| `http://localhost:8080/redirect.html` | Search redirect form |
| `http://localhost:8080/login` | LoginServlet endpoint (POST) |
| `http://localhost:8080/redirect` | RedirectServlet endpoint (GET) |

## Usage Examples

### Login Servlet
1. Navigate to `http://localhost:8080/login.html`
2. Enter username and password
3. Click "Login" to submit
4. View the login result page

### Redirect Servlet
1. Navigate to `http://localhost:8080/redirect.html`
2. Enter a search query (e.g., "Java Servlets")
3. Click "Fetch" to redirect to Google search
4. You will be redirected to: `https://www.google.com/search?q=<your_query>`

## Stopping the Server

Press `Ctrl+C` in the terminal where `mvn tomcat7:run` is running.

## Technologies Used

- **Java Servlets** (javax.servlet)
- **Maven** - Build automation
- **Apache Tomcat 7** - Web server
- **HTML** - Frontend forms
- **CSS** - Styling

## Dependencies

The project uses the following Maven dependency:
```xml
<dependency>
    <groupId>javax.servlet</groupId>
    <artifactId>javax.servlet-api</artifactId>
    <version>4.0.1</version>
    <scope>provided</scope>
</dependency>
```

## Project Configuration

- **Maven Compiler**: Java 1.8 (JDK 8)
- **Tomcat Port**: 8080
- **Application Context**: Root path (`/`)
- **WAR File**: `servlet-assignments.war`

## Troubleshooting

### Port 8080 Already in Use
If you get "Address already in use" error:
```bash
netstat -ano | findstr :8080
taskkill /PID <PID> /F
```

### Compilation Errors
Ensure Maven dependencies are downloaded:
```bash
mvn clean compile
```

### 404 Errors
Make sure you're accessing the correct URL format: `http://localhost:8080/<resource>`

## Author

Created as a servlet simple project for learning Java web development.
