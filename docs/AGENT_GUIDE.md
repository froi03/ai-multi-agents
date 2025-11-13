# Agent System Guide

This guide explains how to work with the AI Multi-Agents system, including agent definitions, usage patterns, and best practices.

## 📖 Table of Contents

- [Overview](#overview)
- [Agent Definitions](#agent-definitions)
- [Agent Capabilities](#agent-capabilities)
- [Using Agents](#using-agents)
- [Agent Collaboration](#agent-collaboration)
- [Prompt Templates](#prompt-templates)
- [Best Practices](#best-practices)

## 🌟 Overview

The AI Multi-Agents system is built on the principle of **specialized expertise**. Instead of a single generalist AI, we use multiple specialized agents, each with focused responsibilities and deep knowledge in their domain.

### Key Benefits

- **Focused Expertise**: Each agent specializes in one area
- **Quality Assurance**: Domain experts produce higher quality output
- **Maintainability**: Clear separation of concerns
- **Scalability**: Easy to add new specialized agents
- **Consistency**: Agents follow established patterns in their domain

### Agent Architecture

```
┌─────────────────────────────────────────┐
│         Task/Feature Request            │
└──────────────┬──────────────────────────┘
               │
               ▼
┌──────────────────────────────────────────┐
│         Agent Router/Orchestrator        │
│    (Determines which agent to use)       │
└──┬───────────┬───────────────┬───────────┘
   │           │               │
   ▼           ▼               ▼
┌────────┐ ┌──────────┐ ┌──────────────┐
│Documen-│ │Scaffolder│ │Test Engineer │
│  ter   │ │  Agent   │ │    Agent     │
└────────┘ └──────────┘ └──────────────┘
```

## 🤖 Agent Definitions

All agents are defined in `.github/agents/` directory using YAML frontmatter and markdown.

### Agent File Structure

```markdown
---
name: agent-name
description: Brief description of agent's role
---

Full agent instructions and responsibilities
```

### Currently Available Agents

| Agent | File | Primary Role |
|-------|------|--------------|
| Documenter | `documenter.agent.md` | Documentation maintenance |
| Scaffolder | `scaffolder.agent.md` | React frontend development |
| Test Engineer | `testengineer.agent.md` | Testing and quality assurance |

## 🎯 Agent Capabilities

### Documenter Agent

**Primary Expertise**: Technical writing, documentation structure, and information architecture

**Capabilities**:
- ✅ Create and maintain README files
- ✅ Write setup and installation guides
- ✅ Document API endpoints and configurations
- ✅ Explain project structure and workflows
- ✅ Maintain consistent documentation style
- ✅ Create navigation and cross-references
- ✅ Update docs to reflect code changes

**When to Use**:
- Creating new documentation
- Updating existing docs after feature changes
- Improving documentation clarity
- Adding examples and guides
- Restructuring documentation

**Example Tasks**:
```
✅ "Document the new authentication flow"
✅ "Create a setup guide for developers"
✅ "Update README with new features"
✅ "Add API documentation for new endpoints"
✅ "Improve contributing guidelines"
```

### Scaffolder Agent

**Primary Expertise**: React development, component architecture, and frontend best practices

**Capabilities**:
- ✅ Implement React components with TypeScript
- ✅ Manage state using hooks and Context API
- ✅ Integrate with REST/GraphQL APIs
- ✅ Ensure responsive design and accessibility
- ✅ Follow React best practices and patterns
- ✅ Optimize component performance
- ✅ Handle loading and error states

**When to Use**:
- Building new React components
- Refactoring frontend code
- Implementing UI features
- Integrating with backend APIs
- Improving component architecture

**Example Tasks**:
```
✅ "Create a reusable Button component"
✅ "Implement user authentication UI"
✅ "Add form validation with error states"
✅ "Build a responsive navigation bar"
✅ "Integrate search functionality with API"
```

### Test Engineer Agent

**Primary Expertise**: Testing strategies, test frameworks, and quality assurance

**Capabilities**:
- ✅ Write unit tests using Jest
- ✅ Create integration tests for components
- ✅ Mock API responses and dependencies
- ✅ Test React components with Testing Library
- ✅ Ensure high code coverage
- ✅ Identify edge cases and race conditions
- ✅ Document test scenarios

**When to Use**:
- Adding tests for new features
- Improving test coverage
- Debugging failing tests
- Testing edge cases
- Setting up test infrastructure

**Example Tasks**:
```
✅ "Write unit tests for the TodoList component"
✅ "Add integration tests for the checkout flow"
✅ "Mock API calls in authentication tests"
✅ "Increase test coverage to 80%"
✅ "Test error handling in form submissions"
```

## 🚀 Using Agents

### Basic Usage Pattern

1. **Identify the Task**: Determine what needs to be done
2. **Select the Agent**: Choose the specialist for the job
3. **Prepare Context**: Gather necessary information
4. **Invoke the Agent**: Use appropriate prompt template
5. **Review Output**: Validate the agent's work

### Agent Invocation Example

For documentation tasks:

```markdown
I need documentation for the new feature. Here's what changed:

**Context:**
- Added gray text color for completed todo items
- Modified: src/css/style.css (line 133)
- Feature improves visual distinction

**Request:**
Using the Documenter agent, please:
1. Update the README with this new feature
2. Add a feature documentation file
3. Update the todo app's README
```

### Decision Tree for Agent Selection

```
Is this about documentation?
├─ Yes → Use Documenter Agent
└─ No
   │
   Is this about UI/components?
   ├─ Yes → Use Scaffolder Agent
   └─ No
      │
      Is this about testing?
      ├─ Yes → Use Test Engineer Agent
      └─ No → Consider creating a new agent
```

## 🤝 Agent Collaboration

Some tasks require multiple agents working together.

### Collaboration Patterns

#### Sequential Collaboration
Agents work one after another:

```
1. Scaffolder: Implements new React component
2. Test Engineer: Writes tests for the component
3. Documenter: Documents the new component API
```

#### Parallel Collaboration
Agents work independently on different aspects:

```
┌─ Scaffolder: Build UI component
├─ Test Engineer: Prepare test infrastructure
└─ Documenter: Draft API documentation
```

#### Iterative Collaboration
Agents refine each other's work:

```
1. Scaffolder: Initial component implementation
2. Test Engineer: Identifies edge cases in tests
3. Scaffolder: Updates component to handle edge cases
4. Documenter: Documents the complete solution
```

### Collaboration Example

**Task**: Add user profile feature

```markdown
**Phase 1 - Planning (Documenter)**
- Document feature requirements
- Create technical specification

**Phase 2 - Implementation (Scaffolder)**
- Build ProfileView component
- Implement profile editing form
- Integrate with backend API

**Phase 3 - Testing (Test Engineer)**
- Write component unit tests
- Add integration tests for API calls
- Test accessibility and edge cases

**Phase 4 - Documentation (Documenter)**
- Update README with new feature
- Document ProfileView API
- Add usage examples
```

## 📝 Prompt Templates

Pre-defined templates are available in `prompt-templates/` directory.

### Using Templates

1. **Navigate to Templates**:
   ```bash
   cd prompt-templates
   ```

2. **Choose Template**: Select based on task type

3. **Customize**: Fill in specific details

4. **Execute**: Use with appropriate agent

### Available Templates

| Template | Purpose | Agent |
|----------|---------|-------|
| `documenter.md` | Documentation tasks | Documenter |
| `scaffolder.md` | Frontend development | Scaffolder |
| `testengineer.md` | Testing tasks | Test Engineer |
| `plan-template.md` | Feature planning | Any |
| `refactoring.md` | Code refactoring | Scaffolder |
| `plan.chatmode.md` | Interactive planning | Any |
| `tdd.chatmode.md` | Test-driven development | Test Engineer |

### Template Customization

Example: Using the documenter template

```markdown
# Original Template
Document the [FEATURE_NAME] by creating:
1. README updates
2. API documentation
3. Usage examples

# Customized
Document the Gray Text Completed Items feature by creating:
1. README updates in main README.md
2. Feature documentation in grey-text-completed-items.md
3. CSS styling examples in documentation
```

## 🎓 Best Practices

### Do's ✅

1. **Use the Right Agent**
   - Match task type to agent expertise
   - Don't use a documenter for coding tasks

2. **Provide Context**
   - Share relevant code, files, and background
   - Explain the goal and constraints

3. **Be Specific**
   - Clear, actionable instructions
   - Define success criteria

4. **Review Output**
   - Validate agent's work
   - Ensure quality standards are met

5. **Iterate as Needed**
   - Refine prompts if output isn't right
   - Provide feedback to improve results

### Don'ts ❌

1. **Don't Mix Responsibilities**
   - Don't ask documenter to write code
   - Don't ask scaffolder to write documentation

2. **Don't Skip Context**
   - Provide necessary background information
   - Don't assume agent knows project state

3. **Don't Accept Without Review**
   - Always validate agent output
   - Check for consistency with project standards

4. **Don't Forget Dependencies**
   - Consider what other agents might need to run
   - Coordinate when multiple agents are involved

5. **Don't Duplicate Work**
   - Check if task is already completed
   - Review existing agent outputs first

### Quality Checklist

Before considering agent work complete:

- [ ] Output matches the request
- [ ] Follows project conventions and standards
- [ ] Integrates with existing code/docs
- [ ] No breaking changes (unless intended)
- [ ] Properly formatted and styled
- [ ] Includes necessary examples
- [ ] Links and references are correct
- [ ] Accessible and user-friendly

## 🔧 Advanced Usage

### Creating Custom Agents

To add a new specialized agent:

1. **Define the Role**: What specific expertise is needed?

2. **Create Agent File**: `.github/agents/new-agent.agent.md`

3. **Write Instructions**:
   ```markdown
   ---
   name: new-agent
   description: Brief description
   ---
   
   Detailed instructions and responsibilities
   ```

4. **Create Template**: Add to `prompt-templates/`

5. **Document Usage**: Update this guide

### Agent Chaining

For complex workflows, chain multiple agents:

```markdown
## Feature: User Authentication

### Step 1: Planning
Agent: Documenter
Task: Create technical specification

### Step 2: Implementation  
Agent: Scaffolder
Task: Build auth components
Dependencies: Step 1 complete

### Step 3: Testing
Agent: Test Engineer
Task: Write comprehensive tests
Dependencies: Step 2 complete

### Step 4: Documentation
Agent: Documenter
Task: Document authentication flow
Dependencies: Step 3 complete
```

## 📚 Additional Resources

- **Agent Definitions**: [.github/agents/](../.github/agents/)
- **Prompt Templates**: [prompt-templates/](../prompt-templates/)
- **Coding Guidelines**: [.github/copilot-instructions.md](../.github/copilot-instructions.md)
- **Contributing Guide**: [CONTRIBUTING.md](../CONTRIBUTING.md)
- **Example Implementation**: [grey-text-completed-items.md](../grey-text-completed-items.md)

## 🆘 Troubleshooting

### Agent Not Understanding Context

**Problem**: Agent produces irrelevant output

**Solution**:
- Provide more specific context
- Reference relevant files explicitly
- Include code examples
- Use appropriate template

### Multiple Agents Needed

**Problem**: Task requires multiple specialties

**Solution**:
- Break task into subtasks
- Assign each subtask to appropriate agent
- Define execution order
- Coordinate outputs

### Output Quality Issues

**Problem**: Agent output doesn't meet standards

**Solution**:
- Review project conventions
- Provide examples of expected output
- Reference style guides
- Iterate with feedback

---

**Need Help?** Open an issue or check the main [README.md](../README.md) for more resources.
