# Feature Flags Module

## Overview
The Feature Flags module provides a flexible and robust feature flag management system, allowing dynamic enabling and disabling of features across the application. It uses Redis for flag storage and provides a REST API for flag management.

## Core Components

### API Layer (`api.py`)
- Implements REST endpoints for feature flag management
- Router endpoints:
  - GET `/feature-flags` - List all flags
  - GET `/feature-flags/{flag_name}` - Get specific flag details
- Error handling and logging integration

### Flag Manager (`flags.py`)
- Core feature flag implementation
- Redis-based storage
- Flag state management
- Configuration handling

## Key Features

### Flag Management
- Enable/disable features dynamically
- Flag state persistence in Redis
- Flag metadata management
- Default state handling

### Redis Integration
- Prefix-based key management
- Flag list maintenance
- State persistence
- Error handling

### API Features
- List all feature flags
- Get individual flag details
- Flag state querying
- Error handling and logging

## Implementation Details

### FeatureFlagManager Class
- Redis integration
- Flag prefix management: `feature_flag:`
- Flag list key: `feature_flags:list`
- Timestamp tracking
- Description support

### Key Methods

#### `set_flag`
- Parameters:
  - key: Flag identifier
  - enabled: Flag state
  - description: Optional description
- Redis state management
- Timestamp tracking
- Error handling

#### `is_enabled`
- Quick flag state checking
- Default state handling
- Error recovery
- Redis integration

## Usage
The module is used for:
- Feature toggling
- A/B testing
- Gradual rollouts
- Feature management
- Configuration control

## Dependencies
- Redis service
- FastAPI framework
- Logging system
- DateTime handling

## Security Notes
- Redis-based storage security
- API endpoint protection
- Error state handling
- Default state safety
