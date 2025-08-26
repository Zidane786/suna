# Knowledge Base Module

## Overview
The Knowledge Base module provides a comprehensive system for managing, storing, and retrieving knowledge entries that can be used by AI agents. It supports various types of content, including text entries and file uploads, with flexible usage contexts and metadata management.

## Core Components

### API Layer (`api.py`)
- Router prefix: `/knowledge-base`
- CRUD operations for knowledge entries
- File upload handling
- Background processing

### File Processor (`file_processor.py`)
- Handles file uploads
- Content extraction
- Metadata processing
- Token counting

## Data Models

### KnowledgeBaseEntry
- Basic entry structure
- Required fields:
  - name: Entry identifier (1-255 chars)
  - content: Main content
- Optional fields:
  - description: Entry description
  - entry_id: Unique identifier
- Configuration:
  - usage_context: always/on_request/contextual
  - is_active: Entry state

### KnowledgeBaseEntryResponse
- Extended entry information
- Additional fields:
  - content_tokens: Token count
  - timestamps (created_at, updated_at)
  - source information
  - file metadata

### Request Models
- CreateKnowledgeBaseEntryRequest
- UpdateKnowledgeBaseEntryRequest
- KnowledgeBaseListResponse

## Key Features

### Entry Management
- Create/Read/Update/Delete operations
- Content validation
- Token counting
- Usage context control

### File Processing
- Upload handling
- Content extraction
- Metadata generation
- Size management

### Access Control
- User authentication
- Agent access verification
- Permission management
- Active state control

## Usage Contexts
1. **Always** - Content always available
2. **On Request** - Available when specifically requested
3. **Contextual** - Used based on context rules

## Dependencies
- FastAPI framework
- Supabase database
- Authentication utilities
- Feature flags system

## Security Features
- User authentication
- Agent access verification
- Content validation
- File type verification

## Integration Points
- Database (Supabase)
- Authentication system
- File processing system
- Feature flags
