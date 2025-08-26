# Backend Documentation Index

## Overview
This index provides links to all backend module documentation, organized by functionality type. The backend is built using FastAPI and provides a comprehensive set of services for managing AI agents, integrations, and various system functionalities.

## Core Components

### Main Application
- [Backend Overview](README.md) - Main backend documentation
- [API Documentation](api.md) - Main API entry point documentation

### Agent and AI Components
- [Agent Module](agent/README.md) - Core agent management and execution
- [AgentPress](agentpress/README.md) - Thread and context management
- [Models](models/README.md) - Language model management and configuration

### Integration Services
- [Composio Integration](composio_integration/README.md) - Composio platform integration
- [MCP Module](mcp_module/README.md) - Model Context Protocol implementation
- [Pipedream](pipedream/README.md) - Workflow automation integration

### Security and Authentication
- [Admin](admin/README.md) - Administrative functions
- [Credentials](credentials/README.md) - Credential management system
- [API Keys](services/api_keys.md) - API key management

### Data Management
- [Knowledge Base](knowledge_base/README.md) - Knowledge storage and retrieval
- [Templates](templates/README.md) - Agent template management
- [Sandbox](sandbox/README.md) - Secure execution environment

### Infrastructure
- [Services](services/README.md) - Core infrastructure services
  - LLM Service
  - Redis Service
  - Email Service
  - Billing Service
  - Supabase Service
  - Transcription Service

### Automation and Control
- [Triggers](triggers/README.md) - Event and automation management
- [Flags](flags/README.md) - Feature flag management

### Utilities
- [Utils](utils/README.md) - Common utilities and helpers
  - Configuration Management
  - Authentication Utilities
  - Helper Functions

## Quick Links

### Getting Started
1. [Backend Overview](README.md)
2. [API Documentation](api.md)
3. [Configuration Guide](utils/README.md)

### Development Guides
1. [Agent Development](agent/README.md)
2. [Template Creation](templates/README.md)
3. [Integration Setup](mcp_module/README.md)

### Security Documentation
1. [Credential Management](credentials/README.md)
2. [Authentication](utils/README.md)
3. [Sandbox Security](sandbox/README.md)

### Infrastructure Setup
1. [Services Overview](services/README.md)
2. [Database Configuration](services/README.md)
3. [Redis Setup](services/README.md)

## Module Dependencies

### Core Dependencies
- FastAPI - Web framework
- Supabase - Database
- Redis - Caching
- JWT - Authentication

### AI/ML Dependencies
- LiteLLM - Model management
- Various LLM providers

### Integration Dependencies
- Composio SDK
- Pipedream API
- MCP Client

## Getting Help
For specific implementation details, refer to the README.md in each module's directory. Each module documentation includes:
- Overview
- Components
- Features
- Dependencies
- Usage examples
- Security considerations
