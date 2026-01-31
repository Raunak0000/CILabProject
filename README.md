# CILabProject

Simple calculator app built with Java 21 and Maven. This is a CI/CD lab project using Jenkins for automation.

## What's Inside

Basic calculator with add functionality (more operations coming later). Includes unit tests and a Jenkins pipeline that handles building, testing, and deployment based on the branch.

## Tech Stack

- Java 21
- Maven
- JUnit 4.13.2
- Jenkins
- Docker

## Project Structure

```
CILabProject/
├── src/
│   ├── main/java/com/muj/ci/
│   │   └── Calculator.java          # Main calculator implementation
│   └── test/java/com/muj/ci/
│       └── CalculatorTest.java      # Unit tests
├── docker/
│   └── Dockerfile                   # Docker container configuration
├── scripts/
│   └── build.bat                    # Build scripts
├── Jenkinsfile                      # Jenkins pipeline configuration
├── pom.xml                          # Maven project configuration
└── README.md
```

## Setup

You'll need Java 21 and Maven installed.

Build:
```bash
mvn clean install
```

Or use the build script on Windows:
```bash
scripts\build.bat
```

Run tests:
```bash
mvn test
```

## CI/CD Pipeline

The project includes a Jenkins pipeline with three stages:

1. **Build & Test**: Compiles the code and runs unit tests on all branches
2. **Security Scan**: Performs security scanning on `release/*` branches
3. **Deploy**: Deploys the application from the `main` branch
Jenkins Pipeline

The Jenkinsfile has three stages:

1. Build & Test - runs on every branch
2. Security Scan - only on release branches
3. Deploy - only on main


There's a Dockerfile in the `docker/` folder using Eclipse Temurin JDK 21.

Build it:
```bash
docker build -f docker/Dockerfile -t cilabproject:latest .
```