# Utils Module

## Overview
The Utils module provides common utilities, helper functions, and shared functionality used throughout the backend application. It includes configuration management, authentication utilities, logging, and various helper functions.

## Core Components

### Configuration (`config.py`)
- Centralized configuration management
- Environment mode handling
- Type validation
- Default values

#### Environment Modes
- LOCAL
- STAGING
- PRODUCTION

#### Key Features
- Environment variable management
- Type checking
- Validation
- Default value handling

### Authentication Utilities (`auth_utils.py`)
- JWT token handling
- User authentication
- Access control
- Cache management

#### Key Functions
- User ID resolution
- Account verification
- Token validation
- Cache handling

### Common Features

#### Configuration Management
- Environment variables
- Type validation
- Default values
- Mode-specific settings

#### Authentication
- JWT processing
- User verification
- Access control
- Cache optimization

#### Caching
- Redis integration
- Cache key management
- TTL handling
- Error recovery

## Key Components

### Environment Configuration
- Mode management
- Variable validation
- Type checking
- Default handling

### Security Utilities
- Token processing
- Authentication
- Authorization
- Access control

### Caching System
- Redis integration
- Key management
- TTL configuration
- Error handling

### Helper Functions
- Data validation
- Type checking
- Error handling
- Utility operations

## Usage

### Configuration
```python
from utils.config import config

# Access configuration
api_key = config.OPENAI_API_KEY
env_mode = config.ENV_MODE
```

### Authentication
```python
from utils.auth_utils import get_current_user_id_from_jwt

# Verify user
user_id = await get_current_user_id_from_jwt(token)
```

## Dependencies
- FastAPI framework
- Redis
- JWT
- Sentry
- Database connection

## Security Features
- JWT validation
- Cache security
- Access control
- Error boundaries

## Integration Points
- Redis caching
- Database connection
- Authentication system
- Logging system

## Error Handling
- Comprehensive error types
- Cache fallbacks
- Validation errors
- Security exceptions
