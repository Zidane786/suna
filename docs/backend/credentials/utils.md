# Credential Utilities (utils.py)

## Overview
The `utils.py` file provides utility functions for credential validation, mapping, and processing within the credentials system.

## Key Functions

### `validate_config_not_empty`
- Validates that credential configurations are not empty
- Input: Dictionary of configuration values
- Raises ValueError if config is empty
- Returns validated configuration

### `validate_credential_mappings`
- Validates credential mappings against requirements
- Parameters:
  - mappings: Dictionary of credential mappings
  - requirements: List of MCPRequirement objects
- Returns list of missing mappings
- Used for ensuring all required credentials are mapped

### `get_missing_credentials_advanced`
- Advanced credential validation
- Features:
  - Checks for required credentials
  - Handles custom credential types
  - Pattern matching for custom credentials
- Parameters:
  - user_credentials: List of MCPCredential objects
  - requirements: List of MCPRequirement objects
- Returns list of missing requirements

### `decode_mcp_qualified_name`
- Decodes URL-encoded MCP qualified names
- Uses urllib.parse for decoding
- Ensures proper handling of special characters

## Usage
These utilities are used for:
- Configuration validation
- Credential requirement checking
- Mapping validation
- Custom credential type handling
- MCP name processing

## Dependencies
- urllib.parse for URL decoding
- credential_service models (MCPRequirement, MCPCredential)
- Python typing module for type hints
