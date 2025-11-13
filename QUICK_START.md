# Quick Start Examples

This guide provides practical examples to help you get started with the AI Multi-Agents system.

## 🎯 Quick Examples

### Example 1: Adding Documentation for a New Feature

**Scenario**: You've just implemented a new feature and need to document it.

**Steps**:

1. **Identify the task**: Documentation needed for new feature
2. **Select agent**: Documenter (documentation specialist)
3. **Prepare context**:
   ```
   Feature: Gray text for completed items
   Files changed: src/css/style.css (line 133)
   Change: Added color: #999; to checked items
   ```

4. **Invoke the agent**:
   ```markdown
   @documenter
   
   I need documentation for a new feature:
   
   Feature: Gray text for completed todo items
   Implementation: Added `color: #999;` to the CSS selector 
   `.item>input[type="checkbox"]:checked+label`
   
   Please create:
   1. Feature documentation file following the template in grey-text-completed-items.md
   2. Update main README.md to mention this feature
   3. Update todo-list-typescript-main/README.md with feature details
   ```

5. **Review output**: Check generated documentation for accuracy and completeness

**Expected Outcome**:
- New feature documentation file created
- README files updated
- Consistent formatting and style

---

### Example 2: Building a React Component

**Scenario**: You need a new reusable button component.

**Steps**:

1. **Identify the task**: Create React component
2. **Select agent**: Scaffolder (React frontend developer)
3. **Use template**: `prompt-templates/scaffolder.md`

4. **Invoke the agent**:
   ```markdown
   @scaffolder
   
   Create a reusable Button component with the following requirements:
   
   - TypeScript interface for props
   - Support for different variants (primary, secondary, danger)
   - Accessible with proper ARIA labels
   - Loading state with spinner
   - Disabled state
   - Click handler prop
   
   Component should follow React best practices and be styled with CSS modules.
   ```

5. **Test the component**: Verify functionality and styling

**Expected Outcome**:
- `Button.tsx` component file
- TypeScript interfaces
- Proper accessibility
- Reusable and maintainable code

---

### Example 3: Adding Tests for a Component

**Scenario**: You need comprehensive tests for the Button component.

**Steps**:

1. **Identify the task**: Write tests
2. **Select agent**: Test Engineer (testing specialist)
3. **Prepare context**: Share the component code

4. **Invoke the agent**:
   ```markdown
   @testengineer
   
   Write comprehensive tests for the Button component:
   
   Component code: [paste Button.tsx code]
   
   Test requirements:
   - Unit tests for all props
   - Test different variants (primary, secondary, danger)
   - Test loading and disabled states
   - Test click handler invocation
   - Test accessibility (ARIA labels, keyboard navigation)
   - Mock any external dependencies
   
   Use Jest and React Testing Library.
   ```

5. **Run tests**: Execute and verify all tests pass

**Expected Outcome**:
- `Button.test.tsx` test file
- High code coverage
- Edge cases covered
- Accessibility tests included

---

### Example 4: Multi-Agent Collaboration

**Scenario**: Implement complete user profile feature (requires all three agents).

**Steps**:

**Phase 1: Documentation & Planning (Documenter)**
```markdown
@documenter

Create a technical specification for a user profile feature:

Requirements:
- View user information
- Edit profile fields (name, email, avatar)
- Save changes to backend
- Responsive design
- Form validation

Please create:
1. Technical specification document
2. User stories
3. Acceptance criteria
```

**Phase 2: Implementation (Scaffolder)**
```markdown
@scaffolder

Based on the specification in [doc link], implement the user profile feature:

Components needed:
- ProfileView (display user data)
- ProfileEditForm (edit mode)
- AvatarUpload (image upload)

Requirements:
- TypeScript interfaces for user data
- Form validation with error messages
- Loading and error states
- Responsive design
- Accessibility support
```

**Phase 3: Testing (Test Engineer)**
```markdown
@testengineer

Write comprehensive tests for the user profile components:

Components: ProfileView, ProfileEditForm, AvatarUpload

Test coverage needed:
- Unit tests for each component
- Integration tests for form submission
- Mock API responses
- Test validation logic
- Test error handling
- Test accessibility
```

**Phase 4: Final Documentation (Documenter)**
```markdown
@documenter

Document the completed user profile feature:

Implementation details: [provide component info]
API integration: [provide API details]

Please create:
1. Feature documentation
2. API usage guide
3. Update main README
4. Add code examples
```

**Expected Outcome**:
- Complete feature implementation
- Comprehensive test coverage
- Full documentation
- Team coordination across specialties

---

## 🚀 Common Workflows

### Workflow 1: Bug Fix

```markdown
1. Identify bug and root cause
2. @scaffolder: Implement fix
3. @testengineer: Add regression test
4. @documenter: Update relevant docs if needed
```

### Workflow 2: New Feature

```markdown
1. @documenter: Create specification
2. @scaffolder: Implement feature
3. @testengineer: Write tests
4. @documenter: Document feature
```

### Workflow 3: Refactoring

```markdown
1. @testengineer: Ensure existing tests are comprehensive
2. @scaffolder: Refactor code
3. @testengineer: Verify tests still pass
4. @documenter: Update docs if architecture changes
```

### Workflow 4: Documentation Update

```markdown
1. @documenter: Review current documentation
2. @documenter: Identify gaps and outdated content
3. @documenter: Update and improve docs
4. @documenter: Add examples and guides
```

---

## 💡 Tips for Success

### Writing Good Agent Prompts

**✅ Good Prompt**:
```markdown
@documenter

Create API documentation for the new authentication endpoints:

Endpoints:
- POST /api/auth/login
- POST /api/auth/logout
- POST /api/auth/refresh

Include:
1. Request/response schemas
2. Authentication requirements
3. Error responses
4. Code examples in JavaScript
5. Rate limiting information
```

**❌ Bad Prompt**:
```markdown
@documenter

Document the auth stuff.
```

**Why?**
- Good prompt is specific and detailed
- Lists exact requirements
- Provides context
- Defines success criteria

### Choosing the Right Agent

| Task | Right Agent | Wrong Agent |
|------|-------------|-------------|
| Write README | Documenter ✅ | Scaffolder ❌ |
| Build UI component | Scaffolder ✅ | Test Engineer ❌ |
| Add unit tests | Test Engineer ✅ | Documenter ❌ |
| Update API docs | Documenter ✅ | Scaffolder ❌ |
| Fix React bug | Scaffolder ✅ | Documenter ❌ |

### Agent Collaboration Checklist

When using multiple agents:

- [ ] Define clear phases and order
- [ ] Ensure each agent has necessary context from previous phases
- [ ] Review each agent's output before proceeding
- [ ] Maintain communication between agents (share relevant outputs)
- [ ] Validate final result integrates all contributions

---

## 🎓 Learning Resources

### For New Users

Start with these examples in order:

1. **Example 1**: Documentation (simplest, single agent)
2. **Example 2**: React component (intermediate)
3. **Example 3**: Testing (builds on Example 2)
4. **Example 4**: Multi-agent (advanced, requires coordination)

### Practice Projects

Try these to build familiarity:

**Beginner**:
- Document an existing feature
- Add a simple CSS change
- Write tests for existing code

**Intermediate**:
- Create a new React component with tests
- Refactor a component with documentation update
- Add a feature requiring two agents

**Advanced**:
- Implement a complex feature with all three agents
- Set up a new project with full documentation
- Create custom agent for specific needs

---

## 📚 Reference Templates

### Documenter Agent Invocation

```markdown
@documenter

[Clear description of documentation task]

Context:
- What changed or was added
- Relevant files and code
- Target audience

Requirements:
1. Specific deliverable 1
2. Specific deliverable 2
3. Specific deliverable 3

Format: [Specify format if needed]
Style: [Reference style guide if applicable]
```

### Scaffolder Agent Invocation

```markdown
@scaffolder

[Description of component or feature to build]

Requirements:
- Requirement 1
- Requirement 2
- Requirement 3

Technical constraints:
- TypeScript required
- Must be accessible (WCAG AA)
- Responsive design
- [Other constraints]

Integration:
- Where it fits in the app
- What it connects to
```

### Test Engineer Agent Invocation

```markdown
@testengineer

[Description of what needs testing]

Code to test: [Provide or link to code]

Test requirements:
- Coverage: [percentage or areas]
- Test types: [unit, integration, e2e]
- Edge cases: [specific scenarios]
- Mocking: [what needs to be mocked]

Frameworks: [Jest, React Testing Library, etc.]
```

---

## 🔗 Next Steps

After trying these examples:

1. **Read the guides**:
   - [Agent System Guide](docs/AGENT_GUIDE.md)
   - [Prompt Chain Guide](docs/PROMPT_CHAIN_GUIDE.md)

2. **Review the templates**:
   - Check `prompt-templates/` directory
   - Customize for your needs

3. **Explore the codebase**:
   - See `.github/copilot-instructions.md`
   - Review `.results/` analyses

4. **Start contributing**:
   - Read [CONTRIBUTING.md](CONTRIBUTING.md)
   - Pick an issue or feature
   - Use the appropriate agent

---

**Questions?** Check the [documentation index](docs/README.md) or open an issue on GitHub!
