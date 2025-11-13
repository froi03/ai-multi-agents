# Documentation Index

Welcome to the AI Multi-Agents documentation! This index helps you navigate all available documentation resources.

## 📚 Main Documentation

### Getting Started

| Document | Description | Audience |
|----------|-------------|----------|
| [README.md](../README.md) | Project overview and quick start | Everyone |
| [QUICK_START.md](../QUICK_START.md) | Practical examples and workflows | New users |
| [CONTRIBUTING.md](../CONTRIBUTING.md) | Contribution guidelines | Contributors |
| [FEATURES.md](../FEATURES.md) | Features overview and roadmap | Product users |
| [CHANGELOG.md](../CHANGELOG.md) | Version history | Everyone |
| [understanding-code.md](../understanding-code.md) | Prompt chain workflow overview | Advanced users |

### Guides

| Guide | Description | Audience |
|-------|-------------|----------|
| [Agent System Guide](AGENT_GUIDE.md) | How to use AI agents effectively | Developers |
| [Prompt Chain Guide](PROMPT_CHAIN_GUIDE.md) | Multi-step analysis workflow | AI practitioners |

## 🤖 Agent Documentation

### Agent Definitions

Located in `.github/agents/`:

| Agent | File | Purpose |
|-------|------|---------|
| Documenter | [documenter.agent.md](../.github/agents/documenter.agent.md) | Documentation maintenance |
| Scaffolder | [scaffolder.agent.md](../.github/agents/scaffolder.agent.md) | React frontend development |
| Test Engineer | [testengineer.agent.md](../.github/agents/testengineer.agent.md) | Testing and QA |

### Prompt Templates

Located in `prompt-templates/`:

- [documenter.md](../prompt-templates/documenter.md) - Documentation tasks
- [scaffolder.md](../prompt-templates/scaffolder.md) - Frontend development
- [testengineer.md](../prompt-templates/testengineer.md) - Testing tasks
- [plan-template.md](../prompt-templates/plan-template.md) - Feature planning
- [refactoring.md](../prompt-templates/refactoring.md) - Code refactoring
- [plan.chatmode.md](../prompt-templates/plan.chatmode.md) - Interactive planning
- [tdd.chatmode.md](../prompt-templates/tdd.chatmode.md) - Test-driven development

## 🔧 Technical Documentation

### Coding Guidelines

| Document | Description |
|----------|-------------|
| [Copilot Instructions](../.github/copilot-instructions.md) | Comprehensive AI coding guidelines |

### Analysis Results

Located in `.results/`:

#### Tech Stack
- [1-techstack.md](../.results/1-techstack.md) - Technology inventory

#### Domain Analyses

Located in `.results/4-domains/`:

- [accessibility.md](../.results/4-domains/accessibility.md) - Accessibility patterns
- [application-initialization.md](../.results/4-domains/application-initialization.md) - App startup
- [data-layer.md](../.results/4-domains/data-layer.md) - State management
- [event-handling.md](../.results/4-domains/event-handling.md) - Event patterns
- [styling.md](../.results/4-domains/styling.md) - CSS conventions
- [typescript-configuration.md](../.results/4-domains/typescript-configuration.md) - TypeScript setup
- [ui-rendering.md](../.results/4-domains/ui-rendering.md) - DOM manipulation

#### Style Guides

Located in `.results/5-style-guides/`:

- [entry-point.md](../.results/5-style-guides/entry-point.md) - App initialization patterns
- [models.md](../.results/5-style-guides/models.md) - Data model patterns
- [styles.md](../.results/5-style-guides/styles.md) - CSS styling patterns
- [templates.md](../.results/5-style-guides/templates.md) - UI template patterns

## 📝 Feature Documentation

### Implemented Features

| Feature | Documentation | Status |
|---------|---------------|--------|
| Gray Text for Completed Items | [grey-text-completed-items.md](../grey-text-completed-items.md) | ✅ Completed |

## 🎓 Learning Paths

### For New Users

Start with these examples in order:

1. Start with [README.md](../README.md) for project overview
2. Try [QUICK_START.md](../QUICK_START.md) practical examples
3. Review [CONTRIBUTING.md](../CONTRIBUTING.md) if contributing
4. Explore [Agent System Guide](AGENT_GUIDE.md) for agent usage
5. Check [Copilot Instructions](../.github/copilot-instructions.md) for coding standards

### Frontend Developers

1. Review [Scaffolder Agent](../.github/agents/scaffolder.agent.md)
2. Check [UI Rendering Analysis](../.results/4-domains/ui-rendering.md)
3. Study [Templates Style Guide](../.results/5-style-guides/templates.md)
4. Use [Scaffolder Template](../prompt-templates/scaffolder.md)

### QA Engineers

1. Review [Test Engineer Agent](../.github/agents/testengineer.agent.md)
2. Study testing patterns in codebase
3. Use [Test Engineer Template](../prompt-templates/testengineer.md)
4. Check [TDD Chat Mode](../prompt-templates/tdd.chatmode.md)

### Documentation Writers

1. Review [Documenter Agent](../.github/agents/documenter.agent.md)
2. Study [Documentation Style](AGENT_GUIDE.md#documenter-agent)
3. Use [Documenter Template](../prompt-templates/documenter.md)
4. Follow [Contributing Guidelines](../CONTRIBUTING.md#documentation-guidelines)

### AI Practitioners

1. Study [Prompt Chain Guide](PROMPT_CHAIN_GUIDE.md)
2. Review [understanding-code.md](../understanding-code.md)
3. Explore prompt chain files in `understanding-code/instruction-generation/`
4. Examine results in `.results/` directory

## 🔍 Quick Reference

### Finding Information

**Question: How do I add a new feature?**
- See [CONTRIBUTING.md](../CONTRIBUTING.md#pull-request-process)
- Review [Agent System Guide](AGENT_GUIDE.md#using-agents)
- Check [Copilot Instructions](../.github/copilot-instructions.md#feature-scaffold-guide)

**Question: How do I use agents?**
- Read [Agent System Guide](AGENT_GUIDE.md)
- Check agent definitions in `.github/agents/`
- Use templates from `prompt-templates/`

**Question: What are the coding standards?**
- Review [Copilot Instructions](../.github/copilot-instructions.md)
- Check [CONTRIBUTING.md](../CONTRIBUTING.md#coding-standards)
- Explore style guides in `.results/5-style-guides/`

**Question: How does the prompt chain work?**
- Read [Prompt Chain Guide](PROMPT_CHAIN_GUIDE.md)
- Review [understanding-code.md](../understanding-code.md)
- Check prompt files in `understanding-code/instruction-generation/`

**Question: Where is feature X documented?**
- Check [Feature Documentation](#feature-documentation) section above
- Search in main [README.md](../README.md)
- Look for `.md` files in root directory

## 📂 File Organization

```
ai-multi-agents/
├── README.md                          # Main project overview
├── CONTRIBUTING.md                    # Contribution guidelines
├── understanding-code.md              # Prompt chain overview
├── grey-text-completed-items.md      # Feature documentation
│
├── .github/
│   ├── agents/                       # Agent definitions
│   │   ├── documenter.agent.md
│   │   ├── scaffolder.agent.md
│   │   └── testengineer.agent.md
│   └── copilot-instructions.md       # Coding guidelines
│
├── docs/                             # Documentation guides
│   ├── README.md                     # This file
│   ├── AGENT_GUIDE.md               # Agent usage guide
│   └── PROMPT_CHAIN_GUIDE.md        # Prompt chain guide
│
├── prompt-templates/                 # Reusable prompts
│   ├── documenter.md
│   ├── scaffolder.md
│   ├── testengineer.md
│   └── ...
│
├── .results/                         # Analysis outputs
│   ├── 1-techstack.md
│   ├── 4-domains/
│   └── 5-style-guides/
│
└── understanding-code/               # Prompt chain
    └── instruction-generation/
        ├── 1-determine-techstack.md
        ├── 2-categorize-files.md
        ├── 3-identify-architecture.md
        ├── 4-domain-deep-dive.md
        ├── 5-styleguide-generation.md
        └── 6-build-instructions.md
```

## 🔗 External Resources

- [GitHub Copilot Documentation](https://docs.github.com/en/copilot)
- [TypeScript Documentation](https://www.typescriptlang.org/docs/)
- [Vite Documentation](https://vitejs.dev/guide/)
- [WCAG Accessibility Guidelines](https://www.w3.org/WAI/WCAG21/quickref/)

## 💡 Tips

### Searching Documentation

Use your editor's search function or `grep`:

```bash
# Search all markdown files for a term
grep -r "singleton pattern" *.md docs/ .github/

# Find files containing "agent"
find . -name "*.md" -type f -exec grep -l "agent" {} \;
```

### Navigating in VS Code

1. Open Command Palette (Cmd/Ctrl + Shift + P)
2. Type "Go to File" (Cmd/Ctrl + P)
3. Start typing the filename

### Documentation Updates

If you find documentation issues:

1. Open an issue on GitHub
2. Submit a PR with corrections
3. Tag the Documenter agent for review

## 🆘 Support

- **Questions**: Open a GitHub Discussion
- **Bugs**: File a GitHub Issue
- **Contributions**: See [CONTRIBUTING.md](../CONTRIBUTING.md)

---

**Last Updated**: November 2025  
**Maintained By**: Documenter Agent

For the most up-to-date information, always refer to the [main README](../README.md).
