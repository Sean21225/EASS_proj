# Job Application Management Platform

A cutting-edge job application management platform that revolutionizes global job hunting through intelligent technologies and comprehensive career support.

## Features

- **User Authentication**: Secure JWT-based authentication with bcrypt password hashing
- **Resume Management**: Create, edit, and manage multiple resume versions
- **Application Tracking**: Track job applications with status updates and notes
- **Resume Optimization**: AI-powered resume analysis and improvement suggestions
- **Job Search**: Search for jobs across LinkedIn, Indeed, Glassdoor, and other major job sites
- **Company Information**: Get detailed company insights and data
- **Analytics Dashboard**: Track application statistics and success rates

## Tech Stack

- **Backend**: FastAPI with Python 3.11
- **Frontend**: React 18 with modern UI components
- **Database**: PostgreSQL with SQLAlchemy ORM
- **Authentication**: JWT tokens with secure password hashing
- **APIs**: JSearch API for job data, custom resume optimization service
- **Deployment**: Docker containers with Docker Compose

## Project Structure

```
├── app/
│   ├── backend/           # FastAPI backend application
│   │   ├── routers/       # API route handlers
│   │   ├── services/      # External service integrations
│   │   ├── main.py        # FastAPI application entry point
│   │   ├── models.py      # Database models
│   │   ├── schemas.py     # Pydantic schemas
│   │   ├── auth.py        # Authentication utilities
│   │   ├── database.py    # Database configuration
│   │   ├── requirements.txt # Backend dependencies
│   │   └── Dockerfile     # Backend container configuration
│   └── frontend/          # React frontend application
│       ├── src/           # React source code
│       ├── public/        # Static assets
│       ├── package.json   # Frontend dependencies
│       ├── nginx.conf     # Nginx configuration
│       └── Dockerfile     # Frontend container configuration
├── integration_test.py    # End-to-end integration tests
├── docker-compose.yml     # Container orchestration
└── README.md             # Documentation
```

## Prerequisites

### For Docker Deployment (Recommended)
- [Docker](https://docs.docker.com/get-docker/) (20.10+)
- [Docker Compose](https://docs.docker.com/compose/install/) (2.0+)
- Git for cloning the repository

### For Local Development
- [Node.js](https://nodejs.org/) (18+) and npm
- [Python](https://python.org/) (3.11+) and pip
- [PostgreSQL](https://postgresql.org/) (15+)
- Git for cloning the repository

## Quick Start

### Using Docker (Recommended)

1. Clone the repository:
   ```bash
   git clone <your-repo-url>
   cd job-application-management
   ```

2. Start the application:
   ```bash
   docker-compose up --build
   ```

3. Access the application:
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:8000
   - API Documentation: http://localhost:8000/docs

The application works out of the box with no configuration required. Docker Compose automatically:
- Sets up PostgreSQL database
- Starts all services with proper health checks
- Provides automatic dependency management

### Local Development

#### Backend Setup

1. Set up PostgreSQL database:
   ```bash
   # Create database and user
   createdb jobapp_management
   createuser jobapp_user --pwprompt
   # Grant privileges to user on database
   ```

2. Navigate to backend directory:
   ```bash
   cd app/backend
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Set up environment variables:
   ```bash
   export DATABASE_URL="postgresql://jobapp_user:your_password@localhost:5432/jobapp_management"
   export SECRET_KEY="your-secret-key-here"
   export JWT_SECRET_KEY="your-jwt-secret-here"
   ```

4. Run the backend:
   ```bash
   python main.py
   ```

#### Frontend Setup

1. Navigate to frontend directory:
   ```bash
   cd app/frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up environment variables:
   ```bash
   echo "REACT_APP_API_BASE_URL=http://localhost:8000" > .env
   ```

4. Start the development server:
   ```bash
   npm start
   ```

## Environment Variables

The application works out of the box without any configuration. All required environment variables are automatically configured by Docker Compose.

### Optional External API Keys

For enhanced job search functionality, you can optionally create a `.env` file in the root directory with these optional API keys:

- `JSEARCH_API_KEY`: RapidAPI key for JSearch API (comprehensive job search)
- `ADZUNA_API_KEY`: Adzuna API key for additional job listings
- `ADZUNA_APP_ID`: Adzuna application ID

**Note**: The application includes free job search APIs that work without any keys, so external API keys are purely optional for additional job sources.

## API Documentation

The backend provides comprehensive API documentation:
- Interactive docs: http://localhost:8000/docs
- OpenAPI spec: http://localhost:8000/openapi.json

### Key Endpoints

- `POST /auth/signup` - User registration
- `POST /auth/login` - User authentication
- `GET /applications` - List job applications
- `POST /applications` - Create new application
- `GET /resume` - List user resumes
- `POST /resume` - Create new resume
- `POST /services/optimize` - Optimize resume content
- `GET /services/jobs/search` - Search for jobs

## Testing

### Integration Tests

Run comprehensive integration tests:
```bash
python integration_test.py
```

### Unit Tests

Backend unit tests:
```bash
cd app/backend
pytest
```

Frontend tests:
```bash
cd app/frontend
npm test
```

## Deployment

### Docker Production Deployment

1. Build production images:
   ```bash
   docker-compose -f docker-compose.prod.yml build
   ```

2. Deploy with proper environment variables:
   ```bash
   docker-compose -f docker-compose.prod.yml up -d
   ```

### Cloud Deployment

The application is designed to deploy easily on:
- AWS ECS/Fargate
- Google Cloud Run
- Azure Container Instances
- Heroku
- DigitalOcean App Platform

## Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Make your changes and add tests
4. Run tests and ensure they pass
5. Submit a pull request

## Security

- All passwords are hashed using bcrypt
- JWT tokens for secure authentication
- Input validation and sanitization
- SQL injection protection through ORM
- CORS configuration for cross-origin requests


## Support

For support and questions:
- Check the API documentation at `/docs`
- Review the integration tests for usage examples
- Open an issue on GitHub

## Changelog

- **June 2025**: Initial release with full-stack implementation
- **June 2025**: Added React frontend integration
- **June 2025**: Implemented free resume optimization service
- **June 2025**: Integrated JSearch API for comprehensive job search
- **June 2025**: Reorganized project structure for better maintainability

## Youtube video demo link
https://youtu.be/Kmeh-G32HiE
