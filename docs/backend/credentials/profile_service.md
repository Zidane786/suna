# Profile Service (profile_service.py)

## Overview
The `profile_service.py` file implements the credential profile management system, allowing users to create and manage multiple configurations for the same credential type.

## Key Components

### Data Models

1. `MCPCredentialProfile`
   - Manages credential profile information
   - Properties:
     - profile_id: Unique identifier
     - account_id: Associated account
     - mcp_qualified_name: MCP identifier
     - profile_name: Profile identifier
     - display_name: Human-readable name
     - config: Profile configuration
     - is_active: Status flag
     - is_default: Default profile indicator
     - Timestamps for tracking usage and modifications

2. `CredentialMapping`
   - Links credentials to profiles
   - Properties:
     - qualified_name: MCP identifier
     - profile_id: Profile identifier
     - profile_name: Profile name
     - display_name: Human-readable name

3. `ProfileRequest`
   - Structure for profile creation requests
   - Supports default profile designation

### Error Handling
- `ProfileNotFoundError`: Handles missing profile scenarios

### Security Features
- Integrates with EncryptionService
- Uses Fernet encryption for sensitive data
- Implements UUID for unique identification
- Uses hashlib for data hashing
- Includes base64 encoding for data storage

## Dependencies
- cryptography.fernet: For encryption
- Supabase: Database connection
- EncryptionService from credential_service
- Standard Python libraries (uuid, json, etc.)

## Usage
This service is used for:
- Creating and managing credential profiles
- Setting default profiles
- Mapping credentials to profiles
- Tracking profile usage and modifications
- Securing profile configurations
