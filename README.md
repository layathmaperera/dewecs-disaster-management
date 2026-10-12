# DEWECS

## Smart Disaster Early-Warning and Emergency Coordination System for Sri Lanka

This project was developed as a 3rd Year, 2nd Semester academic project for SE3070, Group 18. DEWECS is a disaster early-warning and emergency coordination system designed for Sri Lanka. It combines a Spring Boot web dashboard for officers with a Flutter mobile app for citizens to report hazards and track incident response.

## Project overview

This repository contains a monorepo for the DEWECS system:

- `backend/` — Java 21 / Spring Boot 3.5.16 web application for officer workflows
- `mobile/` — Flutter app for citizen hazard reporting and field operations
- `doc/` — API docs, database scripts, demo materials, and Postman collections
- `PROGRESS_NOTES.md` — project status and development notes

The system supports use cases such as:

- warning issuance and hazard event handling
- shelter and rescue coordination
- relief supply and distribution tracking
- ground report review and actioning
- post-event reporting and analysis

## Architecture

### Backend

The backend is a Thymeleaf-based Spring application with:

- Java 21
- Spring Boot 3.5.16
- Maven
- Spring Web, Spring Data JPA, Bean Validation
- PostgreSQL / Neon support and H2 for tests and local demos
- JUnit 5 and Mockito test coverage

It provides the web dashboard and JSON API endpoints used by the mobile application.

### Mobile app

The mobile application is built with Flutter and supports:

- citizen identification
- reporting hazards with photo and GPS data
- offline queueing and retry logic
- viewing report status and history
- shelter/rescue operations through officer APIs

## Repository structure

```text
.
├── backend/                  # Spring Boot backend for officer workflows
├── mobile/                   # Flutter app for citizen reporting and field operations
├── doc/                      # API docs, schema scripts, samples, screenshots, and collections
├── PROGRESS_NOTES.md          # academic project status and development notes
├── README.md                 # project overview and setup guide
├── .gitignore
└── LICENSE                   # add if required for public release
```

## Academic context

This project was developed as part of a university-level software engineering coursework and demonstrates:

- full-stack application development
- system design and requirement implementation
- database-driven backend services
- mobile application development
- API design and integration
- project documentation and testing workflows

## Requirements

### Backend

- Java 21+
- Maven
- PostgreSQL database or H2 for local/test usage

### Mobile app

- Flutter SDK
- Android SDK / emulator or physical Android device

## Quick start

### 1. Run the backend

From the project root:

```bash
cd backend
mvn spring-boot:run
```

For the local demo profile:

```bash
cd backend
mvn spring-boot:run -Dspring-boot.run.profiles=local
```

The app is typically available at:

```text
http://localhost:8080
```

### 2. Run the mobile app

```bash
cd mobile
flutter pub get
flutter run
```

## Environment configuration

The backend expects database settings via environment variables such as:

```powershell
$env:DB_URL = "jdbc:postgresql://<host>/<database>?sslmode=require"
$env:DB_USERNAME = "<user>"
$env:DB_PASSWORD = "<password>"
```

The project includes example configuration and local profile support for easier setup and demos.

## Documentation

Useful documentation is available in the `doc/` folder:

- `doc/MOBILE_API.md` — mobile API reference
- `doc/DEWECS.postman_collection.json` — backend route examples
- `doc/DEWECS-mobile-api.postman_collection.json` — mobile API collection
- `doc/neon-*` scripts — database preparation and schema checks
- `doc/DEMO_SCRIPT.md` — demo walkthrough

## Testing

### Backend

```bash
cd backend
mvn test
mvn verify
```

### Mobile

```bash
cd mobile
flutter test
```


