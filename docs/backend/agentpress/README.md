# AgentPress Module

## Overview
AgentPress is a sophisticated module that manages conversation threads, context windows, and tool interactions for AI agents. It provides essential functionality for maintaining conversation context, managing tokens, and handling tool interactions within the agent system.

## Core Components

### Context Manager (`context_manager.py`)
- Manages conversation context and token limits
- Handles thread summarization
- Implements token counting
- Default token threshold: 120,000 tokens
- Tool result message detection and processing

### Response Processor (`response_processor.py`)
- Processes agent responses
- Formats message content
- Handles different response types
- Manages response validation

### Thread Manager (`thread_manager.py`)
- Manages conversation threads
- Handles message history
- Implements context window management
- Controls conversation flow

### Tool Registry (`tool_registry.py`)
- Registers available tools
- Manages tool configurations
- Handles tool execution
- Validates tool responses

### XML Tool Parser (`xml_tool_parser.py`)
- Parses XML-based tool definitions
- Validates tool configurations
- Manages tool parameters
- Handles tool response formatting

## Key Features

### Context Management
- Token counting and monitoring
- Automatic thread summarization
- Context window optimization
- Tool result processing

### Thread Handling
- Conversation state management
- Message history tracking
- Context preservation
- Token limit enforcement

### Tool Integration
- Tool registration system
- XML-based tool configuration
- Tool execution management
- Response validation

## Usage
The AgentPress module is used for:
- Managing agent conversations
- Processing tool interactions
- Maintaining context windows
- Handling response formatting
- Managing conversation threads

## Dependencies
- LiteLLM for token counting
- Supabase for database operations
- Model manager for LLM interactions
- Custom logging system

## Example Implementation
The module includes an example folder demonstrating:
- Basic usage patterns
- Tool integration
- Context management
- Thread handling
