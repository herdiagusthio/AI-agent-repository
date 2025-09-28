# Metadata Schema

This document defines the structure and requirements for the `metadata.json` file that each agent must include.

## Schema Overview

The metadata file provides structured information about each agent for categorization, discovery, and usage guidance.

## Required Fields

### Basic Information
```json
{
  "agent_id": "string",           // Unique identifier (kebab-case)
  "name": "string",               // Human-readable display name
  "version": "string",            // Semantic version (e.g., "1.0.0")
  "description": "string",        // One-line description
  "category": "string",           // Primary category
  "author": {                     // Author information
    "name": "string",
    "email": "string",
    "github": "string"
  },
  "creation_date": "string",      // ISO date format
  "license": "string"             // License type
}
```

## Optional Fields

### Extended Information
```json
{
  "subcategory": "string",        // More specific categorization
  "detailed_description": "string", // Extended description
  "last_updated": "string",       // ISO date format
  "tags": ["string"],            // Array of tags for search
  "complexity": "string",        // beginner|intermediate|advanced
  "use_cases": ["string"]        // Array of use case descriptions
}
```

### Technical Requirements
```json
{
  "requirements": {
    "minimum_context": "number",     // Minimum context window needed
    "recommended_context": "number", // Recommended context window
    "languages": ["string"],         // Supported languages
    "special_requirements": ["string"] // Any special requirements
  }
}
```

### Performance Characteristics
```json
{
  "performance": {
    "response_time": "string",    // fast|medium|slow
    "accuracy": "string",         // high|medium|low
    "consistency": "string"       // high|medium|low
  }
}
```

### Interaction Details
```json
{
  "interactions": {
    "input_types": ["string"],    // Expected input types
    "output_types": ["string"],   // Output types produced
    "interactive": "boolean"      // Single-turn or multi-turn
  }
}
```

## Field Specifications

### agent_id
- **Format**: kebab-case (lowercase with hyphens)
- **Requirements**: Must be unique across all agents
- **Examples**: `code-reviewer`, `email-composer`, `data-analyzer`

### category
- **Options**: 
  - `conversational` - Chat and dialogue agents
  - `task-specific` - Specific task automation
  - `creative` - Content and creative generation
  - `analytical` - Analysis and research
  - `utility` - Helper and utility functions

### complexity
- **Options**:
  - `beginner` - Easy to use, minimal configuration
  - `intermediate` - Some configuration or domain knowledge needed
  - `advanced` - Complex setup or specialized knowledge required

### version
- **Format**: Semantic versioning (MAJOR.MINOR.PATCH)
- **Examples**: `1.0.0`, `2.1.3`, `0.5.0-beta`

### tags
- **Purpose**: Improve discoverability and categorization
- **Guidelines**: 
  - Use lowercase
  - Include relevant technology names
  - Add functional keywords
  - Maximum 10 tags per agent

## Validation Rules

### Required Validation
- All required fields must be present
- `agent_id` must be unique
- `version` must follow semantic versioning
- `category` must be one of the defined options
- Dates must be in ISO format (YYYY-MM-DD)

### Recommended Validation
- `description` should be 50-100 characters
- `detailed_description` should be 200-500 characters
- `tags` array should have 3-8 items
- Author email should be valid format

## Examples

### Minimal Example
```json
{
  "agent_id": "simple-helper",
  "name": "Simple Helper",
  "version": "1.0.0",
  "description": "Basic assistance agent for general questions",
  "category": "conversational",
  "author": {
    "name": "John Doe",
    "email": "john@example.com",
    "github": "johndoe"
  },
  "creation_date": "2024-01-01",
  "license": "MIT"
}
```

### Complete Example
```json
{
  "agent_id": "advanced-code-reviewer",
  "name": "Advanced Code Reviewer",
  "version": "2.1.0",
  "description": "Comprehensive code analysis with security and performance insights",
  "detailed_description": "An advanced code review agent that performs deep analysis including security vulnerability detection, performance optimization suggestions, and architectural recommendations.",
  "category": "task-specific",
  "subcategory": "code-analysis",
  "author": {
    "name": "Jane Smith",
    "email": "jane@company.com",
    "github": "janesmith"
  },
  "creation_date": "2024-01-15",
  "last_updated": "2024-03-20",
  "license": "MIT",
  "tags": ["code-review", "security", "performance", "architecture", "best-practices"],
  "complexity": "intermediate",
  "use_cases": [
    "Enterprise code review automation",
    "Security audit preparation",
    "Performance optimization analysis",
    "Code quality standardization"
  ],
  "requirements": {
    "minimum_context": 4000,
    "recommended_context": 8000,
    "languages": ["english", "spanish"],
    "special_requirements": ["Programming experience recommended"]
  },
  "performance": {
    "response_time": "medium",
    "accuracy": "high",
    "consistency": "high"
  },
  "interactions": {
    "input_types": ["code", "text", "files"],
    "output_types": ["structured-report", "recommendations"],
    "interactive": true
  }
}
```

## Maintenance

- Update `last_updated` when making changes
- Increment `version` following semantic versioning
- Keep `tags` current and relevant
- Review and update `use_cases` based on feedback

This schema ensures consistent metadata across all agents, enabling effective categorization, search, and usage guidance.