# Backend API (api.py)

## Overview
The `api.py` file serves as the main FastAPI application entry point for the backend service. It initializes and configures the core components of the application, including database connections, service integrations, and API routes.

## Key Components

### Application Initialization
- Uses FastAPI framework for the REST API
- Implements an asynchronous lifespan manager for application startup and shutdown
- Configures environment variables using dotenv
- Integrates Sentry for error tracking

### Core Services Initialization
- Database connection (Supabase)
- Redis connection for caching and temporary storage
- Agent API initialization
- Sandbox environment setup
- Authentication and API keys management
- Feature flags system
- Transcription services
- Email services
- Trigger system

### Resource Management
- Implements proper cleanup of resources during shutdown
- Handles database disconnection
- Manages Redis connection lifecycle
- Cleans up agent resources

### Rate Limiting
- Implements IP-based rate limiting
- Configures maximum concurrent IP connections (25)

### Platform Compatibility
- Special handling for Windows platform using WindowsProactorEventLoopPolicy

## Dependencies
- FastAPI - Web framework
- Redis - Caching and temporary storage
- Supabase - Database connection
- Sentry - Error tracking
- Various internal services (billing, flags, transcription, etc.)

## Usage
This file serves as the main entry point for the backend service and should be run using a ASGI server like uvicorn:
```bash
uvicorn api:app --reload
```
