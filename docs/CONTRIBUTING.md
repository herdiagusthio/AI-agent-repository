# Contributing to AI Agent Repository

Thank you for your interest in contributing to the AI Agent Repository! This document provides guidelines for adding new agents and improving existing ones.

## 🎯 How to Contribute

### Adding a New Agent

1. **Fork the Repository**
   - Click the "Fork" button on the GitHub repository page
   - Clone your fork locally

2. **Choose the Right Category**
   - `conversational/` - Chat agents, virtual assistants, role-playing
   - `task-specific/` - Code review, email writing, data processing
   - `creative/` - Writing, storytelling, brainstorming
   - `analytical/` - Data analysis, research, reporting
   - `utility/` - Formatting, translation, summarization

3. **Create Your Agent Directory**
   ```bash
   cd agents/[category]
   mkdir your-agent-name
   cd your-agent-name
   ```

4. **Use the Template**
   Copy files from `templates/agent-template/` as a starting point

5. **Required Files**
   - `README.md` - Agent documentation
   - `config.json` - Configuration settings
   - `prompt.txt` - Main prompt/instructions
   - `metadata.json` - Agent metadata

## 📝 Agent Guidelines

### Naming Convention
- Use lowercase with hyphens: `task-scheduler-agent`
- Be descriptive but concise
- Avoid generic names like "helper" or "assistant"

### Documentation Standards
- Clear, concise descriptions
- Include usage examples
- Document limitations and requirements
- Specify target audience/difficulty level

### Quality Standards
- Test your agent thoroughly
- Provide realistic examples
- Include edge cases in documentation
- Ensure prompts are well-structured

## 🔍 Review Process

1. **Self-Review Checklist**
   - [ ] All required files present
   - [ ] Documentation is complete and clear
   - [ ] Examples work as expected
   - [ ] Metadata is accurate
   - [ ] No sensitive information included

2. **Submission**
   - Create a pull request
   - Use descriptive title: "Add [agent-name] to [category]"
   - Include summary of what the agent does
   - Tag relevant reviewers if known

3. **Review Criteria**
   - Functionality and usefulness
   - Documentation quality
   - Code organization
   - Adherence to guidelines

## 🚫 What Not to Include

- Personal information or credentials
- Copyrighted content without permission
- Malicious or harmful prompts
- Incomplete or untested agents
- Duplicate functionality without improvement

## 💡 Tips for Success

- Start simple and iterate
- Study existing agents for inspiration
- Focus on one specific use case per agent
- Write clear, actionable prompts
- Include error handling in your documentation

## 📞 Getting Help

- Open an issue for questions
- Check existing agents for examples
- Review the documentation in `/docs/`
- Join discussions in pull requests

## 🏆 Recognition

Contributors will be:
- Listed in the agent's metadata
- Mentioned in release notes for significant contributions
- Invited to be maintainers for active contributors

Thank you for making the AI Agent Repository better for everyone!