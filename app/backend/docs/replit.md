# Job Application Management Platform

## Overview

A complete full-stack job application management platform with FastAPI backend and React frontend. The system provides comprehensive job tracking, resume management with intelligent optimization, user authentication, and a modern web interface for job seekers to manage their entire application process.

## System Architecture

**Backend Framework**: FastAPI with automatic OpenAPI documentation
- RESTful API design with proper HTTP status codes
- Async/await support for improved performance
- Built-in request/response validation with Pydantic

**Database Layer**: PostgreSQL with SQLAlchemy ORM
- Relational database design with proper foreign key relationships
- Connection pooling and session management
- Database migrations through SQLAlchemy metadata

**Authentication**: JWT-based authentication with bcrypt password hashing
- Secure token-based authentication
- Password hashing using industry-standard bcrypt
- Role-based access control for protected endpoints

## Project Structure

The project follows a clean directory structure:

```
├── app/
│   ├── backend/           # FastAPI backend application (Ex1)
│   │   ├── routers/       # API route handlers
│   │   ├── services/      # External service integrations
│   │   ├── docs/          # Project documentation
│   │   ├── main.py        # FastAPI application entry point
│   │   ├── models.py      # Database models
│   │   ├── schemas.py     # Pydantic schemas
│   │   ├── auth.py        # Authentication utilities
│   │   └── database.py    # Database configuration
│   └── frontend/          # React frontend application (Ex2)
│       ├── src/           # React source code
│       ├── public/        # Static assets
│       └── package.json   # Frontend dependencies
├── integration_test.py    # End-to-end integration tests
├── docker-compose.yml     # Container orchestration
└── README.md             # Main project documentation
```

## Recent Changes

- **June 30, 2025**: Final project structure reorganization completed
- Moved all backend files to app/backend directory (main.py, models.py, schemas.py, auth.py, database.py)
- Moved routers and services directories to app/backend
- Consolidated duplicate files, keeping the most recent versions
- Created integration_test.py in root directory for end-to-end testing
- Created docker-compose.yml for container orchestration
- Created comprehensive README.md with setup and deployment instructions
- Updated workflow configurations to run from correct directories
- Removed all duplicate files and directories from root to maintain clean structure
- Moved all configuration files (requirements.txt, package.json) to appropriate subdirectories
- Organized documentation files in app/backend/docs/

## User Preferences

Preferred communication style: Simple, everyday language.