# AI Multi-Agents System

A comprehensive framework for building and managing specialized AI agents that collaborate to complete development tasks. This repository demonstrates how multiple AI agents can work together, each with their own expertise, to deliver high-quality software development outcomes.

## 🌟 Overview

This project showcases an innovative approach to AI-assisted development using specialized agents:

- **Documenter Agent**: Maintains clear, accurate, and up-to-date project documentation
- **Scaffolder Agent**: Develops responsive and maintainable user interfaces using React
- **Test Engineer Agent**: Designs and maintains comprehensive test coverage

Each agent is defined with specific responsibilities, ensuring focused expertise and consistent quality across different aspects of development.

## 📁 Project Structure

```
ai-multi-agents/
├── .github/
│   ├── agents/                    # Agent definitions
│   │   ├── documenter.agent.md
│   │   ├── scaffolder.agent.md
│   │   └── testengineer.agent.md
│   └── copilot-instructions.md    # Comprehensive coding guidelines
├── .results/                      # Analysis results from prompt chain
│   ├── 1-techstack.md
│   ├── 4-domains/                # Domain-specific analysis
│   └── 5-style-guides/           # Style guide documentation
├── prompt-templates/              # Reusable agent prompt templates
├── understanding-code/            # Prompt chain instructions
│   └── instruction-generation/
├── todo-list-typescript-main/     # Example TypeScript todo application
└── grey-text-completed-items.md   # Feature implementation documentation
```

## 🚀 Quick Start

### Prerequisites

- Node.js 16+ and npm
- Git
- A code editor with GitHub Copilot (optional but recommended)

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/froi03/ai-multi-agents.git
   cd ai-multi-agents
   ```

2. Install dependencies for the todo app:
   ```bash
   cd todo-list-typescript-main
   npm install
   ```

3. Run the development server:
   ```bash
   npm run dev
   ```

## 🤖 Understanding the Agents

### Documenter Agent

**Role**: Documentation specialist ensuring all project materials are easy to read, navigate, and maintain.

**Responsibilities**:
- Create and update documentation files (README.md, CONTRIBUTING.md, docs/)
- Provide clear setup and installation instructions
- Explain project structure, key scripts, and development workflows
- Document API endpoints, configuration options, and environment variables
- Maintain consistent writing style with proper headings, tables, and examples

### Scaffolder Agent (React Frontend Developer)

**Role**: Frontend development specialist focused on building user-facing applications with React.

**Responsibilities**:
- Implement reusable and responsive React components
- Apply hooks, Context API, or modern state libraries for state management
- Integrate REST or GraphQL APIs with proper error handling
- Ensure accessibility (a11y), responsive design, and high performance
- Follow best practices for clean, maintainable code

### Test Engineer Agent

**Role**: Testing specialist ensuring reliability through automated tests.

**Responsibilities**:
- Write and maintain unit and integration tests
- Ensure high coverage across components, hooks, and API interactions
- Mock API responses and external dependencies effectively
- Automate regression testing for critical user flows
- Detect edge cases, race conditions, and performance bottlenecks early

## 📚 Multi-Step Prompt Chain

This repository includes a sophisticated prompt chain for generating comprehensive coding guidelines. The workflow is defined in `understanding-code.md` and consists of:

1. **Determine Tech Stack** - Identify technologies and dependencies
2. **Categorize Files** - Organize codebase by file types and patterns
3. **Identify Architecture** - Analyze architectural patterns and conventions
4. **Domain Deep Dive** - Explore domain-specific patterns
5. **Style Guide Generation** - Create category-specific style guides
6. **Build Instructions** - Generate final comprehensive instructions

Results are stored in `.results/` and compiled into `.github/copilot-instructions.md`.

## 🎯 Example: Todo List TypeScript Application

The repository includes a vanilla TypeScript todo list application demonstrating the architectural patterns and coding conventions.

### Recent Features

#### Gray Text for Completed Items
A visual enhancement that makes completed todo items appear with gray text color (#999), improving the distinction between active and completed tasks.

**Implementation**:
- Modified: `todo-list-typescript-main/src/css/style.css`
- Added `color: #999;` to `.item>input[type="checkbox"]:checked+label` selector
- Maintains WCAG AA accessibility with 5.9:1 contrast ratio
- Status: ✅ Completed (November 6, 2025)

See `grey-text-completed-items.md` for detailed implementation documentation.

## 🛠️ Development Workflow

### Using the Agents

1. **Review agent definitions** in `.github/agents/` to understand their capabilities
2. **Invoke appropriate agents** for specific tasks based on their expertise
3. **Collaborate between agents** for complex features requiring multiple specialties
4. **Follow coding guidelines** defined in `.github/copilot-instructions.md`

### Making Changes

1. Create a feature branch
2. Make focused, minimal changes following the style guides
3. Use appropriate agent templates from `prompt-templates/`
4. Run linters and tests before committing
5. Document changes in markdown files when applicable

## 📖 Documentation

- **[Copilot Instructions](.github/copilot-instructions.md)**: Comprehensive coding guidelines
- **[Understanding Code](understanding-code.md)**: Prompt chain workflow overview
- **[Agent Definitions](.github/agents/)**: Individual agent specifications
- **[Prompt Templates](prompt-templates/)**: Reusable agent prompts
- **[Analysis Results](.results/)**: Tech stack and domain analysis

## 🤝 Contributing

Contributions are welcome! Please see our [contribution guidelines](CONTRIBUTING.md) for details on:

- Code of conduct
- Development setup
- Coding standards
- Pull request process
- Testing requirements

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🔗 Resources

- [Live Demo](https://awesome-todo-list-nkq0.onrender.com/) - Todo List Application
- [GitHub Copilot Documentation](https://docs.github.com/en/copilot)
- [TypeScript Documentation](https://www.typescriptlang.org/docs/)

## 💡 Best Practices

- **Agent Specialization**: Always delegate to the most appropriate agent for the task
- **Minimal Changes**: Make the smallest possible changes to achieve goals
- **Documentation First**: Document features before, during, and after implementation
- **Test Coverage**: Ensure all new features include appropriate tests
- **Accessibility**: Maintain WCAG AA compliance in all UI changes
- **Consistency**: Follow established patterns and conventions

## 📞 Support

For questions, issues, or suggestions:
- Open an issue on GitHub
- Review existing documentation in the repo
- Check the `.results/` folder for analysis insights

---

**Built with ❤️ using AI Multi-Agents**
