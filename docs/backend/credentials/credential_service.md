# Credential Service (credential_service.py)

## Overview
The `credential_service.py` file implements the core credential management functionality, handling the storage, encryption, and retrieval of Model Context Protocol (MCP) credentials.

## Key Components

### Data Models

1. `MCPCredential`
   - Core credential data structure
   - Properties:
     - credential_id: Unique identifier
     - account_id: Associated account
     - mcp_qualified_name: MCP identifier
     - display_name: Human-readable name
     - config: Credential configuration
     - is_active: Status flag
     - Timestamps for tracking usage and modifications

2. `MCPRequirement`
   - Defines requirements for MCP credentials
   - Properties:
     - qualified_name: MCP identifier
     - display_name: Human-readable name
     - enabled_tools: List of enabled tools
     - required_config: Required configuration fields
     - custom_type: Optional type specification

3. `CredentialRequest`
   - Structure for credential creation requests
   - Handles account association and configuration

### Error Handling
- `CredentialNotFoundError`: Handles missing credential scenarios
- `CredentialAccessDeniedError`: Manages unauthorized access attempts

### Security Features
- Implements Fernet encryption for sensitive data
- Uses UUID for unique identification
- Includes hashlib for data hashing
- Base64 encoding for data storage

## Dependencies
- cryptography.fernet: For encryption
- Supabase: Database connection
- Standard Python libraries (os, json, uuid, etc.)

## Usage
This service is used for:
- Storing encrypted credentials
- Retrieving and validating credentials
- Managing MCP requirements
- Handling credential access control
- Tracking credential usage and modifications
