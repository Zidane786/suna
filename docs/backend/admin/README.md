# Admin Module

## Overview
The admin module provides administrative functionality for managing system-wide settings, user installations, and environment configurations. It's designed to be accessed only by authenticated administrators and includes special endpoints for system management.

## Components

### API (`api.py`)
- Router prefix: `/admin`
- Tags: `["admin"]`

#### Key Endpoints

1. **Suna Agent Installation** (`/suna-agents/install-user/{account_id}`)
   - Installs Suna agent for specific users
   - Supports replacement of existing installations
   - Requires admin API key authentication
   - Returns installation status and agent ID

2. **Environment Variables Management** (`/env-vars`)
   - Available only in local mode
   - Retrieves current environment variables
   - Supports .env file management
   - Security-restricted functionality

### Security Features
- Admin API key verification
- Environment mode restrictions
- Error handling and logging
- Access control mechanisms

### Dependencies
- FastAPI framework
- Environment configuration management
- Suna default agent service
- Logging system
- Authentication utilities

## Core Features

### User Management
- Installation of Suna agents for users
- User-specific configuration management
- Installation status tracking

### Environment Management
- Environment variable access
- Local mode configurations
- .env file handling
- Security restrictions

### Error Handling
- HTTP exception management
- Logging of administrative actions
- Security violation handling
- Installation failure management

## Usage
- Administrative tasks
- User setup and configuration
- Environment management
- System monitoring
- Security enforcement

## Security Notes
- Restricted to admin users only
- Environment-specific restrictions
- API key verification required
- Logging of all administrative actions
