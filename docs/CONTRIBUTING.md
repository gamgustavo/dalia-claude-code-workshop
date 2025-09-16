# Contributing to Claude Code Workshop Website

Thank you for your interest in contributing to the Claude Code Workshop website! This document provides guidelines and information for contributors.

## Getting Started

1. Fork the repository
2. Clone your fork locally
3. Create a new branch for your feature or fix
4. Make your changes
5. Test your changes locally
6. Submit a pull request

## Development Setup

```bash
# Clone your fork
git clone https://github.com/YOUR_USERNAME/dalia-claude-code-workshop.git
cd dalia-claude-code-workshop

# Install dependencies
npm install

# Start development server
npm run dev
```

## Code Standards

### HTML
- Use semantic HTML5 elements
- Include proper accessibility attributes
- Follow proper document structure
- Use lowercase for all file names

### CSS
- Use CSS custom properties (variables) when possible
- Follow BEM naming convention for classes
- Keep styles organized and modular
- Ensure responsive design principles

### JavaScript
- Use modern ES6+ syntax
- Keep code clean and well-commented
- Follow consistent formatting

## Testing

Before submitting your changes:

```bash
# Validate HTML
npm test

# Format code
npm run format

# Lint JavaScript
npm run lint
```

## Commit Messages

Use clear, descriptive commit messages:
- Use present tense ("Add feature" not "Added feature")
- Keep the first line under 50 characters
- Include more details in the body if needed

## Pull Request Process

1. Ensure your code follows the established standards
2. Update documentation if needed
3. Test your changes thoroughly
4. Create a detailed pull request description
5. Link any relevant issues

## Questions?

If you have questions, feel free to:
- Open an issue for discussion
- Contact the maintainers
- Join our workshop community

Thank you for contributing!