# Prompt Chain Workflow Guide

This guide explains the multi-step prompt chain system used to generate comprehensive coding guidelines from existing codebases.

## 📖 Table of Contents

- [Overview](#overview)
- [Workflow Steps](#workflow-steps)
- [Running the Prompt Chain](#running-the-prompt-chain)
- [Output Structure](#output-structure)
- [Understanding Results](#understanding-results)
- [Customization](#customization)

## 🌟 Overview

The prompt chain is a systematic approach to analyzing a codebase and generating AI-friendly coding instructions. It transforms existing code patterns into explicit guidelines that AI assistants (like GitHub Copilot) can follow.

### Purpose

- **Extract Patterns**: Identify architectural patterns and conventions from existing code
- **Document Standards**: Create explicit style guides for different file categories
- **Enable Consistency**: Help AI generate code that matches project standards
- **Reduce Errors**: Prevent AI from introducing incompatible patterns

### Key Components

```
Input: Source Code (./todo-list-typescript-main)
   ↓
Process: Multi-Step Analysis (./understanding-code/instruction-generation)
   ↓
Output: Coding Guidelines (.github/copilot-instructions.md)
```

## 🔄 Workflow Steps

The prompt chain consists of 6 sequential steps, each building on the previous one.

### Step 1: Determine Tech Stack

**File**: `understanding-code/instruction-generation/1-determine-techstack.md`

**Purpose**: Identify all technologies, frameworks, and dependencies used in the codebase.

**Analysis**:
- Package dependencies (package.json)
- Build tools and configuration
- Runtime vs. development dependencies
- Language versions and features

**Output**: `.results/1-techstack.md`

**Example Output**:
```markdown
## Core Technologies
- TypeScript 5.0.2
- Vite 4.4.5 (build tool)

## Dependencies
- Zero runtime dependencies
- Build tools only: TypeScript compiler, Vite

## Language Features
- ES2020 target
- Strict TypeScript mode
```

### Step 2: Categorize Files

**File**: `understanding-code/instruction-generation/2-categorize-files.md`

**Purpose**: Group files by their role and responsibility in the application.

**Analysis**:
- File structure and organization
- Naming conventions
- Functional categories (models, views, styles, etc.)
- Pattern identification

**Output**: Categories identified (used in next steps)

**Example Categories**:
```
1. Models - Data and state management
2. Templates - UI rendering
3. Entry Point - Application initialization
4. Styles - CSS styling
5. HTML Templates - Static HTML structure
6. Build Configuration - TypeScript/build setup
```

### Step 3: Identify Architecture

**File**: `understanding-code/instruction-generation/3-identify-architecture.md`

**Purpose**: Recognize architectural patterns and design decisions.

**Analysis**:
- Design patterns (Singleton, Observer, etc.)
- State management approach
- Data flow architecture
- Rendering strategy

**Output**: Architectural understanding (feeds into step 4)

**Key Patterns Identified**:
```
- Singleton pattern for models and templates
- Imperative DOM manipulation (no framework)
- localStorage persistence
- Event-driven architecture
- Full re-render strategy
```

### Step 4: Domain Deep Dive

**File**: `understanding-code/instruction-generation/4-domain-deep-dive.md`

**Purpose**: Analyze domain-specific patterns in depth.

**Analysis**:
- Domain-specific conventions
- Integration patterns
- Constraint identification
- Best practices extraction

**Output**: `.results/4-domains/` directory with domain analyses

**Generated Files**:
```
.results/4-domains/
├── accessibility.md
├── application-initialization.md
├── data-layer.md
├── event-handling.md
├── styling.md
├── typescript-configuration.md
└── ui-rendering.md
```

### Step 5: Style Guide Generation

**File**: `understanding-code/instruction-generation/5-styleguide-generation.md`

**Purpose**: Create category-specific style guides with examples.

**Analysis**:
- Code patterns per category
- Naming conventions
- Structure templates
- Do's and don'ts

**Output**: `.results/5-style-guides/` directory

**Generated Files**:
```
.results/5-style-guides/
├── entry-point.md
├── models.md
├── styles.md
└── templates.md
```

**Example Style Guide** (models.md):
```markdown
## Key Conventions
- ✅ Singleton pattern
- ✅ Private fields with getters/setters
- ✅ Auto-save after mutations
- ❌ No multiple instances

## Example Structure
[Code template]
```

### Step 6: Build Instructions

**File**: `understanding-code/instruction-generation/6-build-instructions.md`

**Purpose**: Compile all analyses into comprehensive coding instructions.

**Compilation**:
- Synthesize all previous steps
- Organize by file category
- Add examples and scaffolds
- Create integration rules

**Output**: `.github/copilot-instructions.md`

**Structure**:
```markdown
1. Overview and architecture summary
2. File category reference (with patterns from steps 1-5)
3. Feature scaffold guide
4. Integration rules (architectural constraints)
5. Example prompts and usage
6. Domain-specific notes
7. Summary checklist
```

## 🚀 Running the Prompt Chain

### Prerequisites

- Understanding of the source codebase
- Familiarity with AI prompting
- Access to an AI assistant (ChatGPT, Claude, Copilot Chat, etc.)

### Execution Process

1. **Review All Steps First**
   ```bash
   cd understanding-code/instruction-generation
   ls -la
   # Read through all .md files to understand the flow
   ```

2. **Execute in Order**
   - Start with `1-determine-techstack.md`
   - Copy the prompt and provide it to your AI assistant
   - Save the AI's response to `.results/1-techstack.md`
   - Move to next step

3. **Provide Context**
   - Share source code when requested
   - Reference previous step outputs
   - Include relevant files

4. **Save Outputs**
   ```bash
   # Example directory structure after completion
   .results/
   ├── 1-techstack.md
   ├── 4-domains/
   │   ├── accessibility.md
   │   ├── data-layer.md
   │   └── ...
   └── 5-style-guides/
       ├── models.md
       ├── templates.md
       └── ...
   ```

5. **Generate Final Output**
   - Execute step 6 last
   - Compile all previous analyses
   - Generate `.github/copilot-instructions.md`

### Example Workflow

```bash
# Step 1: Tech Stack Analysis
cd understanding-code/instruction-generation
cat 1-determine-techstack.md
# Copy prompt, run with AI, save to .results/1-techstack.md

# Step 2: File Categorization
cat 2-categorize-files.md
# Copy prompt, provide source code, identify categories

# Step 3: Architecture Identification
cat 3-identify-architecture.md
# Copy prompt, analyze patterns, document findings

# Step 4: Domain Deep Dive
cat 4-domain-deep-dive.md
# Copy prompt, analyze each domain, save to .results/4-domains/

# Step 5: Style Guide Generation
cat 5-styleguide-generation.md
# Copy prompt, generate guides, save to .results/5-style-guides/

# Step 6: Build Final Instructions
cat 6-build-instructions.md
# Copy prompt, compile everything, save to .github/copilot-instructions.md
```

## 📁 Output Structure

### Analysis Results (.results/)

```
.results/
├── 1-techstack.md                 # Technology inventory
├── 4-domains/                     # Domain-specific analyses
│   ├── accessibility.md           # A11y patterns
│   ├── application-initialization.md
│   ├── data-layer.md             # State management
│   ├── event-handling.md         # Event patterns
│   ├── styling.md                # CSS conventions
│   ├── typescript-configuration.md
│   └── ui-rendering.md           # DOM manipulation
└── 5-style-guides/               # Category style guides
    ├── entry-point.md            # App initialization
    ├── models.md                 # Data models
    ├── styles.md                 # CSS styling
    └── templates.md              # UI templates
```

### Final Output (.github/)

```
.github/
└── copilot-instructions.md       # Comprehensive coding guidelines
```

## 🔍 Understanding Results

### Tech Stack Analysis

**What to look for**:
- Core dependencies vs. dev dependencies
- Framework choices and versions
- Build tool configuration
- Language features enabled

**Usage**: Helps AI understand what libraries and features are available.

### Domain Analyses

**What to look for**:
- Recurring patterns in each domain
- Constraints and requirements
- Integration points
- Best practices

**Usage**: Ensures AI follows domain-specific conventions.

### Style Guides

**What to look for**:
- Code structure templates
- Naming conventions
- Required patterns (✅)
- Prohibited patterns (❌)

**Usage**: Provides concrete examples for AI to follow.

### Final Instructions

**What to look for**:
- Organized by file category
- Clear do's and don'ts
- Example prompts and expected outputs
- Integration rules

**Usage**: Complete reference for AI-assisted development.

## ⚙️ Customization

### Adapting for Different Projects

1. **Modify Source Folder**
   ```markdown
   # In understanding-code.md
   {source_code_folder} = ./your-project-folder
   ```

2. **Adjust Output Locations**
   ```markdown
   {output_folder} = .results
   {final_output_file} = .github/copilot-instructions.md
   ```

3. **Customize Prompts**
   - Edit files in `understanding-code/instruction-generation/`
   - Add project-specific questions
   - Include domain-specific analyses

### Adding New Steps

To add a new analysis step:

1. **Create Prompt File**
   ```bash
   touch understanding-code/instruction-generation/7-new-step.md
   ```

2. **Define Analysis**
   ```markdown
   # New Analysis Step
   
   Analyze [specific aspect] of the codebase:
   - Question 1
   - Question 2
   ```

3. **Update Workflow**
   - Add to `understanding-code.md`
   - Document expected output
   - Update step 6 to include new analysis

### Project-Specific Domains

For specialized projects, add domain analyses:

```bash
# Example: Add API domain for backend projects
touch understanding-code/instruction-generation/4.1-api-domain.md
```

Content example:
```markdown
# API Domain Analysis

Analyze API-specific patterns:
- Endpoint structure
- Authentication approach
- Error handling
- Rate limiting
- Documentation style
```

## 🎯 Best Practices

### Do's ✅

1. **Complete All Steps**: Don't skip steps as they build on each other
2. **Save Outputs**: Store all intermediate results for reference
3. **Provide Context**: Give AI access to actual source code
4. **Review Results**: Validate AI output for accuracy
5. **Iterate**: Refine prompts if results aren't accurate

### Don'ts ❌

1. **Don't Rush**: Each step requires thoughtful analysis
2. **Don't Assume**: Verify AI findings against actual code
3. **Don't Skip Examples**: Include code examples in style guides
4. **Don't Forget Updates**: Rerun when codebase changes significantly
5. **Don't Mix Projects**: Keep analyses separate for different codebases

## 📊 Success Metrics

A successful prompt chain run produces:

- [ ] Complete tech stack inventory
- [ ] All file categories identified
- [ ] Architectural patterns documented
- [ ] Domain-specific analyses completed
- [ ] Category style guides generated
- [ ] Final instructions compiled
- [ ] Examples included for each pattern
- [ ] Integration rules clearly stated

## 🔄 Maintenance

### When to Rerun

- Major architectural changes
- New framework/library additions
- Significant pattern shifts
- New file categories introduced
- After major refactoring

### Incremental Updates

For small changes:
1. Update relevant domain analysis
2. Modify affected style guide
3. Regenerate step 6 (build instructions)

## 📚 Related Documentation

- **Main Workflow**: [understanding-code.md](../understanding-code.md)
- **Agent Guide**: [AGENT_GUIDE.md](AGENT_GUIDE.md)
- **Copilot Instructions**: [.github/copilot-instructions.md](../.github/copilot-instructions.md)
- **Contributing**: [CONTRIBUTING.md](../CONTRIBUTING.md)

---

**Questions?** Open an issue or refer to the main [README.md](../README.md).
