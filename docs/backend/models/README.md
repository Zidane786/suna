# Models Module

## Overview
The Models module manages AI model configurations, capabilities, and pricing across different providers. It provides a centralized system for model management, cost calculation, and capability validation.

## Core Components

### Model Manager (`manager.py`)
- Central model management
- Model resolution
- Validation
- Cost calculation

### Model Definitions (`models.py`)
- Data structures
- Model capabilities
- Pricing configuration
- Provider definitions

### Model Registry (`registry.py`)
- Model registration
- Default models
- Alias management
- Provider mapping

## Key Features

### Model Management
- Model resolution
- Capability validation
- Pricing calculation
- Model state tracking

### Model Structure
#### Provider Support
- OpenAI
- Anthropic
- OpenRouter
- Google
- XAI
- MoonshotAI

#### Capabilities
- Chat
- Function Calling
- Vision
- Code Interpreter
- Web Search
- Thinking
- Structured Output

### Pricing Management
`ModelPricing` class:
- Input cost calculation
- Output cost calculation
- Per-token pricing
- Million-token rates

### Model Configuration
`Model` class properties:
- Unique identifier
- Display name
- Provider
- Aliases
- Context window size
- Output token limits
- Capabilities list
- Pricing information
- Availability status
- Beta status
- Tier access

## Core Functions

### Model Manager
- `get_model`: Model retrieval
- `resolve_model_id`: ID resolution
- `validate_model`: Model validation
- `calculate_cost`: Cost computation

### Default Models
- Premium model configuration
- Free model configuration
- Tier-based access

## Usage
The module is used for:
- Model selection
- Cost estimation
- Capability verification
- Provider management

## Integration Points
- LLM services
- Billing system
- Access control
- Provider APIs

## Dependencies
- Logging system
- Provider integrations
- Registry system
- Type definitions
