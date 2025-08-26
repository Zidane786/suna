# Templates Module

## Overview
The Templates module manages agent templates, allowing users to create, install, and customize agent configurations. It provides functionality for template sharing, versioning, and installation management.

## Core Components

### API Layer (`api.py`)
- Router for template management
- Template CRUD operations
- Installation handling
- Access control

### Template Service
- Template management
- Version control
- Access management
- Default templates

### Installation Service
- Template installation
- Credential validation
- Configuration mapping
- Error handling

## Data Models

### Template Models
- `CreateTemplateRequest`:
  - agent_id
  - make_public flag
  - tags

- `InstallTemplateRequest`:
  - template_id
  - instance_name
  - custom_system_prompt
  - profile_mappings
  - custom_mcp_configs

- `TemplateResponse`:
  - template_id
  - creator_id
  - metadata

### Installation Models
- `TemplateInstallationRequest`
- `TemplateInstallationResult`

## Key Features

### Template Management
- Creation from existing agents
- Public/private visibility
- Tagging system
- Version control

### Installation Handling
- Template installation
- Configuration customization
- Credential mapping
- Error validation

### Access Control
- Creator permissions
- Public access management
- Installation rights
- Version control

## Error Handling
Custom exceptions:
- TemplateNotFoundError
- TemplateAccessDeniedError
- SunaDefaultAgentTemplateError
- TemplateInstallationError
- InvalidCredentialError

## Usage Scenarios

### Template Creation
- Create from existing agents
- Configure visibility
- Add tags
- Set permissions

### Template Installation
- Install with customization
- Map credentials
- Configure MCP settings
- Handle errors

### Template Management
- Version control
- Access management
- Updates and modifications
- Deletion handling

## Dependencies
- FastAPI framework
- Database connection
- Authentication utilities
- Logging system

## Security Features
- Access control
- Credential validation
- Permission management
- Error boundaries

## Integration Points
- Database (Supabase)
- Authentication system
- MCP configuration
- Credential management
