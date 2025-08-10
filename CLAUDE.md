# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Agent OS Framework Overview

Agent OS is a specification framework that transforms AI coding agents from "confused interns" into productive developers by providing structured workflows, standards, and specifications. It creates a contract between human developers and AI assistants through comprehensive documentation layers.

### Core Architecture

**Three-tier specification system:**
1. **Global Standards** (~/.agent-os/standards/) - Universal preferences across all projects
2. **Product Standards** (.agent-os/product/) - Product-specific requirements and decisions  
3. **Spec Standards** (.agent-os/specs/) - Feature-specific technical specifications

**Workflow Commands:**
- `/plan-product` - Initialize new product with documentation structure
- `/create-spec` - Create detailed specifications for features
- `/execute-task` - Implement specifications following TDD approach
- `/analyze-product` - Analyze existing codebases and retrofit Agent OS structure

### Key Directories and Purpose

- **commands/** - Command triggers/aliases for AI assistants
- **instructions/** - Comprehensive workflow instructions (500-900 lines each)
- **standards/** - Global development standards (tech stack, code style, best practices)
- **claude-code/user/** - Claude Code integration and command setup

### Installation & Setup

```bash
# Install Agent OS globally
curl -sSL https://raw.githubusercontent.com/instrumental-products/agent-os/main/setup.sh | bash

# Install Claude Code commands
curl -sSL https://raw.githubusercontent.com/instrumental-products/agent-os/main/setup-claude-code.sh | bash

# Install Cursor rules
curl -sSL https://raw.githubusercontent.com/instrumental-products/agent-os/main/setup-cursor.sh | bash
```

### Main Files Structure

**Standards (automatically installed to ~/.agent-os/):**
- `~/.agent-os/standards/tech-stack.md` - Default technology preferences
- `~/.agent-os/standards/code-style.md` - Coding conventions and formatting
- `~/.agent-os/standards/best-practices.md` - Development philosophies

**Instructions:**
- `instructions/plan-product.md` - 7-step new product initialization
- `instructions/create-spec.md` - 15-step specification creation workflow  
- `instructions/execute-tasks.md` - 12-step task implementation process
- `instructions/analyze-product.md` - 5-step analysis for existing codebases

### Development Workflow

1. **Initialize**: Run `/plan-product` to set up product documentation
2. **Plan**: Use `/create-spec` to break down features into detailed specifications
3. **Build**: Run `/execute-task` to implement specs following test-first approach
4. **Maintain**: Project-specific files in `.agent-os/product/` override global standards

### File Structure for Projects

After setup, projects contain:
```
.agent-os/
├── product/
│   ├── mission.md
│   ├── tech-stack.md
│   ├── roadmap.md
│   └── decisions.md
└── specs/
    └── YYYY-MM-DD-feature-name/
        ├── spec.md
        ├── tasks.md
        └── sub-specs/
```

### Customization Notes

- Global standards are installed to ~/.agent-os/ and can be customized per developer
- Project-level files override globals for product-specific needs
- Decision files have highest authority and can override any standard
- Each instruction file includes validation and error handling for AI assistance