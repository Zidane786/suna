# Credentials Module Overview

## Purpose
The credentials module provides a comprehensive system for managing authentication credentials and profiles within the application. It handles secure storage, retrieval, and management of various types of credentials needed for different services and integrations.

## Core Components

### 1. API Layer (`api.py`)
- Implements REST endpoints for credential management
- Handles credential and profile CRUD operations
- Implements request validation and authentication

### 2. Credential Service (`credential_service.py`)
- Core credential management functionality
- Handles encryption and secure storage
- Manages MCP (Model Context Protocol) credentials
- Implements credential access control

### 3. Profile Service (`profile_service.py`)
- Manages credential profiles
- Supports multiple configurations per credential type
- Handles default profile settings
- Implements profile-specific security measures

### 4. Utilities (`utils.py`)
- Provides helper functions for credential validation
- Implements mapping validation
- Handles MCP name processing
- Supports custom credential types

## Security Features
- Encryption using Fernet
- Secure credential storage
- Access control mechanisms
- Configuration validation
- Secure profile management

## Key Concepts

### MCP (Model Context Protocol)
- Standardized credential format
- Supports multiple credential types
- Enables tool-specific configurations

### Profiles
- Multiple configurations per credential type
- Default profile support
- Active/inactive status tracking
- Usage tracking and timestamps

## Integration Points
- Database (Supabase)
- Authentication system
- API endpoints
- External services
