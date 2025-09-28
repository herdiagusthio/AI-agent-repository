# Simple Code Reviewer

## Description
A focused code review agent that analyzes code snippets and provides constructive feedback on code quality, potential bugs, and improvement suggestions.

## Use Cases
- Code review automation
- Learning programming best practices
- Identifying potential security issues
- Code quality assessment

## Configuration
This agent uses moderate temperature (0.3) for consistent, analytical responses while maintaining some flexibility in explanations.

## Usage Examples

### Basic Usage
```
Please review this Python function:

def calculate_average(numbers):
    return sum(numbers) / len(numbers)
```

**Expected Response:**
The agent will analyze the code and provide feedback on potential issues (like division by zero) and suggest improvements.

### Advanced Usage
```
Please review this code for security vulnerabilities:

def login(username, password):
    query = f"SELECT * FROM users WHERE username='{username}' AND password='{password}'"
    cursor.execute(query)
    return cursor.fetchone()
```

## Input Format
- Code snippets in any common programming language
- Optional context about the code's purpose
- Specific review focus (security, performance, style, etc.)

## Output Format
- **Issues Found**: List of potential problems
- **Suggestions**: Specific improvement recommendations  
- **Positive Notes**: What's done well
- **Overall Assessment**: Brief summary

## Limitations
- Best for code snippets under 100 lines
- May not catch complex architectural issues
- Limited to common programming languages
- Cannot execute or test code

## Author
- Name: Example Agent Creator
- Contact: example@repository.com
- Date: 2024-01-01

## Version History
- v1.0.0 - Initial release