# MCP (Model Context Protocol) Module

## Overview
The MCP Module provides integration with the Model Context Protocol, enabling communication between AI agents and external tools/services. It handles custom tool discovery, connection management, and tool execution within the system.

## Core Components

### API Layer (`api.py`)
- Router for MCP-related endpoints
- Custom tool discovery
- Connection management
- Error handling

### MCP Service (`mcp_service.py`)
- Core MCP functionality
- Connection handling
- Tool execution
- Error management

## Key Features

### Custom Tool Discovery
- Tool type discovery
- Configuration management
- Response handling
- Error processing

### Connection Management
#### Request Models
- CustomMCPConnectionRequest
  - URL configuration
  - Optional settings

#### Response Models
- CustomMCPConnectionResponse
  - Connection status
  - Tool information
  - Configuration details

### Error Handling
Comprehensive error types:
- MCPException (Base)
- MCPConnectionError
- MCPToolNotFoundError
- MCPToolExecutionError
- MCPProviderError
- MCPConfigurationError
- MCPAuthenticationError
- CustomMCPError

### Connection Class
`MCPConnection` dataclass:
- qualified_name: Unique identifier
- name: Display name
- config: Connection configuration
- enabled_tools: Available tools
- provider: Service provider (default: 'custom')

## Integration Features

### Client Integration
- SSE (Server-Sent Events) support
- Streamable HTTP client
- Async operation support
- Session management

### Security
- Authentication handling
- Encryption service integration
- Configuration validation
- Error boundaries

## Dependencies
- MCP client library
- FastAPI framework
- Authentication utilities
- Encryption service

## Usage
The module is used for:
- Discovering custom tools
- Managing MCP connections
- Executing tool operations
- Handling tool configurations

## Security Notes
- Authentication required for endpoints
- Configuration encryption
- Error handling for security
- Access control implementation
