# Sandbox Module

## Overview
The Sandbox module provides a secure environment for executing code and managing file operations using Daytona's sandbox infrastructure. It offers APIs for sandbox management, file operations, and execution control.

## Core Components

### API Layer (`api.py`)
- Router for sandbox operations
- File management endpoints
- Path normalization
- Error handling

### Sandbox Manager (`sandbox.py`)
- Daytona integration
- Sandbox lifecycle management
- Configuration handling
- State management

### Tool Base (`tool_base.py`)
- Base classes for sandbox tools
- Tool execution framework
- Error handling
- Resource management

## Key Features

### Sandbox Management
- Creation and deletion
- State management
- Resource allocation
- Configuration handling

### File Operations
- File upload/download
- Directory management
- Path normalization
- Permission handling

### Configuration
- Daytona API integration
- Environment configuration
- Resource limitations
- Security settings

### State Management
States supported:
- ARCHIVED
- STOPPED
- RUNNING
- ERROR

## Core Functions

### Sandbox Operations
- `get_or_start_sandbox`: Retrieves or initializes sandbox
- `delete_sandbox`: Cleanup and removal
- Path normalization utilities
- State validation

### File Management
`FileInfo` model:
- name: File identifier
- path: File location
- is_dir: Directory flag
- size: File size
- mod_time: Modification time
- permissions: Access rights

## Integration

### Daytona SDK Integration
- AsyncDaytona client
- Configuration management
- Resource allocation
- State tracking

### Security Features
- Path normalization
- Permission validation
- Resource limitations
- Error boundaries

## Configuration
Environment variables:
- DAYTONA_API_KEY
- DAYTONA_SERVER_URL
- DAYTONA_TARGET

## Dependencies
- Daytona SDK
- FastAPI framework
- Database connection
- Authentication utilities

## Usage
The module is used for:
- Secure code execution
- File management
- Resource isolation
- Tool execution

## Docker Integration
- Container management
- Resource isolation
- Environment configuration
- Security boundaries
