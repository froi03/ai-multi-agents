# Contributing to AI Multi-Agents

Thank you for your interest in contributing to the AI Multi-Agents project! This document provides guidelines and instructions for contributing.

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Setup](#development-setup)
- [Working with Agents](#working-with-agents)
- [Coding Standards](#coding-standards)
- [Pull Request Process](#pull-request-process)
- [Documentation Guidelines](#documentation-guidelines)
- [Testing Requirements](#testing-requirements)

## 🤝 Code of Conduct

### Our Pledge

We are committed to providing a welcoming and inspiring community for all. Please be respectful, professional, and constructive in all interactions.

### Expected Behavior

- Use welcoming and inclusive language
- Be respectful of differing viewpoints and experiences
- Gracefully accept constructive criticism
- Focus on what is best for the community
- Show empathy towards other community members

## 🚀 Getting Started

### Prerequisites

Before contributing, ensure you have:

- Node.js 16 or higher
- npm or yarn package manager
- Git version control
- A code editor (VS Code recommended with GitHub Copilot)
- Basic understanding of TypeScript and React

### Finding Work

1. **Check the Issues**: Look for issues labeled `good first issue` or `help wanted`
2. **Agent-Specific Tasks**: Identify which agent is best suited for the work
3. **Propose New Features**: Open an issue to discuss before implementing

## 💻 Development Setup

### Initial Setup

1. Fork the repository on GitHub
2. Clone your fork locally:
   ```bash
   git clone https://github.com/YOUR-USERNAME/ai-multi-agents.git
   cd ai-multi-agents
   ```

3. Add the upstream repository:
   ```bash
   git remote add upstream https://github.com/froi03/ai-multi-agents.git
   ```

4. Install dependencies:
   ```bash
   cd todo-list-typescript-main
   npm install
   ```

### Running the Application

Start the development server:
```bash
npm run dev
```

Build for production:
```bash
npm run build
```

Preview production build:
```bash
npm run preview
```

## 🤖 Working with Agents

### Agent Selection

Choose the appropriate agent based on the task:

| Task Type | Agent | Agent File |
|-----------|-------|------------|
| Documentation updates | Documenter | `.github/agents/documenter.agent.md` |
| React component development | Scaffolder | `.github/agents/scaffolder.agent.md` |
| Test creation/maintenance | Test Engineer | `.github/agents/testengineer.agent.md` |

### Using Agent Templates

Prompt templates are available in `prompt-templates/`:

- `documenter.md` - Documentation tasks
- `scaffolder.md` - Frontend development
- `testengineer.md` - Testing tasks
- `plan-template.md` - Feature planning
- `refactoring.md` - Code refactoring

### Agent Collaboration

For complex features requiring multiple agents:

1. **Plan First**: Create a feature plan documenting all required changes
2. **Delegate Appropriately**: Assign tasks to the right agents
3. **Coordinate**: Ensure agents work sequentially when dependencies exist
4. **Review Together**: Have all affected agents review the final result

## 📏 Coding Standards

### General Principles

Follow the architectural patterns documented in `.github/copilot-instructions.md`:

- **Minimal Changes**: Make the smallest possible modifications
- **Type Safety**: Use explicit TypeScript types everywhere
- **Consistency**: Match existing code patterns and styles
- **Accessibility**: Maintain WCAG AA compliance
- **Documentation**: Update relevant docs with code changes

### TypeScript Standards

```typescript
// ✅ Good - Explicit types, singleton pattern
export default class ListItem implements Item {
  static instance: ListItem = new ListItem();
  
  constructor(
    private _id: string = "",
    private _item: string = ""
  ) {}
  
  get id(): string { return this._id; }
  set id(id: string) { this._id = id; }
}

// ❌ Bad - Implicit any, no types
export default class ListItem {
  constructor(id, item) {
    this.id = id;
    this.item = item;
  }
}
```

### CSS Standards

```css
/* ✅ Good - BEM-like naming, semantic classes */
.newItemEntry__form {
  display: flex;
  gap: 0.25rem;
  font-size: 1.5rem;
}

.newItemEntry__button:hover,
.newItemEntry__button:focus {
  color: limegreen;
}

/* ❌ Bad - Generic names, inline styles */
.btn {
  color: green;
}
```

### File Organization

- **Models**: `src/models/[ModelName].ts` - Data and state management
- **Templates**: `src/templates/[TemplateName].ts` - UI rendering
- **Styles**: `src/css/style.css` - All styling in single file
- **Documentation**: Root level markdown files

## 🔄 Pull Request Process

### Before Submitting

1. **Create a Feature Branch**:
   ```bash
   git checkout -b feature/your-feature-name
   ```

2. **Make Your Changes**:
   - Follow the coding standards
   - Keep changes focused and minimal
   - Update documentation as needed

3. **Test Your Changes**:
   ```bash
   npm run build
   npm run dev
   ```

4. **Run Linters** (if available):
   ```bash
   npm run lint
   ```

5. **Commit with Descriptive Messages**:
   ```bash
   git commit -m "Add gray text styling for completed items"
   ```

### Submitting the PR

1. **Push Your Branch**:
   ```bash
   git push origin feature/your-feature-name
   ```

2. **Create Pull Request**:
   - Use a clear, descriptive title
   - Reference related issues
   - Describe what changed and why
   - Include screenshots for UI changes
   - List which agent(s) were involved

3. **PR Template**:
   ```markdown
   ## Description
   Brief description of changes
   
   ## Related Issues
   Fixes #123
   
   ## Agent(s) Used
   - [x] Documenter
   - [ ] Scaffolder
   - [ ] Test Engineer
   
   ## Changes Made
   - Added gray text color for completed items
   - Updated documentation
   
   ## Screenshots
   [If applicable]
   
   ## Testing Done
   - [x] Manual testing in browser
   - [x] Accessibility verification
   - [ ] Unit tests added
   ```

### Review Process

1. **Automated Checks**: Ensure all CI checks pass
2. **Code Review**: Address reviewer feedback promptly
3. **Documentation Review**: Verify docs are updated
4. **Final Approval**: Maintainer approval required to merge

## 📚 Documentation Guidelines

### What to Document

- **New Features**: Create a feature documentation file (e.g., `feature-name.md`)
- **API Changes**: Update relevant API documentation
- **Configuration**: Document new environment variables or config options
- **Architecture Changes**: Update `.github/copilot-instructions.md`

### Documentation Structure

Feature documentation should include:

```markdown
---
title: Feature Name
version: 1.0
date_created: YYYY-MM-DD
last_updated: YYYY-MM-DD
status: COMPLETED | IN_PROGRESS | PLANNED
---

# Feature Name

**Brief description**: One-line summary

## Implementation Status
Current status and completion date

## Architecture and Design
How it fits into the project

## Tasks
- [ ] Task 1
- [ ] Task 2

## Implementation Details
Code changes and rationale

## Open Questions
Any unresolved questions
```

### Writing Style

- **Clear and Concise**: Use simple language
- **Structured**: Use headings, lists, and tables
- **Examples**: Include code examples where helpful
- **Links**: Reference related documents using relative paths
- **Accessibility**: Ensure documentation is screen-reader friendly

## ✅ Testing Requirements

### Required Tests

For new features, include:

1. **Unit Tests**: Test individual functions and methods
2. **Integration Tests**: Test component interactions
3. **Accessibility Tests**: Verify WCAG compliance
4. **Manual Testing**: Test in actual browsers

### Test Structure

```typescript
// Example test structure (when test infrastructure exists)
describe('ListItem', () => {
  it('should create a new item with default values', () => {
    const item = new ListItem();
    expect(item.id).toBe("");
    expect(item.checked).toBe(false);
  });
});
```

### Testing Checklist

- [ ] All existing tests pass
- [ ] New tests added for new functionality
- [ ] Edge cases covered
- [ ] Accessibility verified
- [ ] Cross-browser tested (Chrome, Firefox, Safari)
- [ ] Mobile responsiveness verified

## 🐛 Bug Reports

When reporting bugs, include:

1. **Clear Title**: Descriptive summary of the issue
2. **Steps to Reproduce**: Detailed steps
3. **Expected Behavior**: What should happen
4. **Actual Behavior**: What actually happens
5. **Environment**: Browser, OS, Node version
6. **Screenshots**: Visual evidence if applicable

## 💡 Feature Requests

When proposing features:

1. **Use Case**: Explain why the feature is needed
2. **Proposed Solution**: Suggest implementation approach
3. **Alternatives**: Consider other approaches
4. **Agent Assignment**: Suggest which agent should handle it
5. **Breaking Changes**: Note if it affects existing functionality

## 📞 Getting Help

- **Documentation**: Check `.github/copilot-instructions.md` first
- **Issues**: Search existing issues for similar problems
- **Discussions**: Use GitHub Discussions for questions
- **Code Review**: Ask for clarification in PR comments

## 🎯 Best Practices

### Development

- **Small Commits**: Make focused, atomic commits
- **Descriptive Messages**: Write clear commit messages
- **Branch Naming**: Use `feature/`, `fix/`, or `docs/` prefixes
- **Stay Updated**: Regularly sync with upstream

### Agent Usage

- **Right Agent for the Job**: Use the specialist for each task type
- **Follow Templates**: Use provided prompt templates
- **Document Intent**: Explain what you want the agent to accomplish
- **Review Output**: Always review and validate agent work

### Code Quality

- **Linting**: Fix all linting errors before committing
- **Type Safety**: No implicit `any` types
- **Accessibility**: Test with screen readers
- **Performance**: Avoid unnecessary re-renders
- **Security**: Never commit secrets or sensitive data

## 📜 License

By contributing, you agree that your contributions will be licensed under the same MIT License that covers the project.

## 🙏 Acknowledgments

Thank you for contributing to AI Multi-Agents! Your efforts help make this project better for everyone.

---

**Questions?** Open an issue or start a discussion on GitHub!
