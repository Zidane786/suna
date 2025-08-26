# Triggers Module

## Overview
The Triggers module manages automated event handling, scheduling, and workflow execution in the system. It provides a flexible framework for creating and managing various types of triggers that can initiate agent actions or workflows.

## Core Components

### API Layer (`api.py`)
- Main router: `/triggers`
- Workflows router: `/workflows`
- Trigger CRUD operations
- Webhook handling
- Schedule management

### Services

#### Trigger Service (`trigger_service.py`)
- Core trigger functionality
- Event processing
- Trigger type management
- Result handling

#### Provider Service (`provider_service.py`)
- Trigger provider management
- Integration handling
- Provider configuration

#### Execution Service (`execution_service.py`)
- Trigger execution
- Workflow management
- Result processing

## Key Models

### Trigger Types (Enum)
- SCHEDULE: Time-based triggers
- WEBHOOK: HTTP webhook triggers
- EVENT: System event triggers

### Data Models

#### TriggerEvent
- trigger_id
- agent_id
- trigger_type
- raw_data
- timestamp
- context

#### TriggerResult
- success status
- execution flags
- agent/workflow data
- error handling
- execution variables

#### Trigger
- Configuration data
- Provider information
- Status management
- Timestamps

### Request/Response Models
- TriggerCreateRequest
- TriggerUpdateRequest
- TriggerResponse

## Key Features

### Trigger Management
- Creation and configuration
- Status tracking
- Update handling
- Deletion management

### Scheduling
- Time-based execution
- Recurring schedules
- Schedule parsing
- Next run calculation

### Webhook Processing
- HTTP endpoint handling
- Payload processing
- Authentication
- Error management

### Event Handling
- System event processing
- Custom event triggers
- Event routing
- Context management

## Integration Points

### External Services
- Database (Supabase)
- Billing system
- Authentication
- Feature flags

### Internal Systems
- Agent execution
- Workflow management
- Provider integration
- Event processing

## Security Features
- HMAC verification
- Access control
- Authentication
- Error boundaries

## Dependencies
- FastAPI framework
- Database connection
- Authentication system
- Billing service
- Feature flags system

## Usage
The module is used for:
- Automated task execution
- Scheduled operations
- Event-driven actions
- Workflow automation

## Error Handling
- Comprehensive error types
- Result validation
- Execution monitoring
- Logging integration
