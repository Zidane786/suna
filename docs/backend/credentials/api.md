# Credentials API (api.py)

## Overview
The `api.py` file in the credentials module implements the API endpoints for managing authentication credentials and profiles in the system. It provides functionality for storing, retrieving, and managing credential configurations and profiles.

## Key Components

### API Router
- Implements a FastAPI router for credential-related endpoints
- Handles authentication using JWT tokens
- Manages credential profiles and configurations

### Models
1. `StoreCredentialRequest`
   - Handles requests for storing new credentials
   - Validates credential configurations
   - Requires MCP qualified name and display name

2. `StoreCredentialProfileRequest`
   - Manages credential profile creation
   - Supports default profile setting
   - Includes configuration validation

3. `BulkDeleteProfilesRequest`
   - Handles bulk deletion of credential profiles
   - Takes a list of profile IDs

4. `CredentialResponse`
   - Defines the structure for credential responses
   - Includes credential identification information

### Services Integration
- Integrates with credential_service for core credential operations
- Uses profile_service for managing credential profiles
- Implements utility functions for configuration validation and MCP name handling

## Dependencies
- FastAPI for API routing
- Supabase database connection
- Authentication utilities
- Credential and Profile services

## Usage
This module is used when:
- Storing new credentials
- Managing credential profiles
- Retrieving credential information
- Validating credential configurations
- Bulk operations on credential profiles
