# Context Manager

## Overview
The Context Manager is a crucial component of the AgentPress system that handles token counting and thread summarization to prevent reaching context window limitations in Language Learning Models (LLMs).

## Class: ContextManager

### Purpose
Manages conversation context while ensuring:
- Token count remains within limits
- Thread context is preserved
- Tool interactions are properly tracked
- Summarization is triggered when needed

### Key Features

#### Token Management
- Default token threshold: 120,000
- Configurable token limits
- Token counting implementation
- Threshold monitoring

#### Message Processing
- Tool result message detection
- JSON content parsing
- Message type validation
- Content format handling

#### Tool Integration
- Tool result validation
- Interactive element handling
- Message content parsing
- Response format management

### Methods

#### `__init__(token_threshold: int = DEFAULT_TOKEN_THRESHOLD)`
- Initializes the context manager
- Sets up database connection
- Configures token threshold

#### `is_tool_result_message(msg: Dict[str, Any]) -> bool`
- Validates tool result messages
- Checks message content format
- Parses JSON content
- Identifies interactive elements

### Integration Points
- Database (Supabase)
- Token counter (LiteLLM)
- Model manager
- Logging system

## Usage
The Context Manager is used to:
- Track token usage in conversations
- Trigger summarization when needed
- Validate tool responses
- Maintain context window limits

## Dependencies
- litellm.utils
- services.supabase
- utils.logger
- models.model_manager
