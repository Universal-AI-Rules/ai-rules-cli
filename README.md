# AI Rules CLI

**Command-line interface for Universal AI Rules** 🛠️

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](../LICENSE)
[![Project Status: Concept](https://img.shields.io/badge/Project%20Status-Concept-orange.svg)](https://github.com/Universal-AI-Rules)

## Overview

The AI Rules CLI is the primary tool for managing Universal AI Rules (`.ai/ai-rules.yaml`) files. It provides commands to initialize, validate, sync, and manage your unified AI assistant rules across all supported tools.

## Vision: How It Would Work

> **⚠️ Note: This CLI doesn't exist yet - we're looking for Node.js/TypeScript developers to help build it!**

### Planned Commands

```bash
# Install globally
npm install -g @universal-ai-rules/cli

# Initialize a new rules file
ai-rules init
ai-rules init --template=web-app
ai-rules init --from-existing

# Validate your rules
ai-rules validate
ai-rules validate --strict

# Sync to all supported AI tools
ai-rules sync
ai-rules sync --tools=cursor,claude,copilot
ai-rules sync --dry-run

# Import from existing tool configs
ai-rules import --from=cursor
ai-rules import --from=claude --merge

# Manage templates
ai-rules templates list
ai-rules templates use next-js
ai-rules templates create my-template

# Check tool support
ai-rules tools list
ai-rules tools check
```

### Example Workflow

```bash
# Start a new project
cd my-project
ai-rules init --template=typescript-react

# Edit your rules
vim .ai/ai-rules.yaml

# Validate before committing
ai-rules validate

# Sync to all your AI tools
ai-rules sync

# Your tools now have consistent rules:
# - .cursor/rules/project.md
# - CLAUDE.md  
# - .github/copilot-instructions.md
# - etc.
```

## Features (Planned)

### Core Commands
- **Initialize** - Create new `.ai/ai-rules.yaml` files
- **Validate** - Check rules against schema and best practices
- **Sync** - Generate tool-specific config files
- **Import** - Convert existing tool configs to unified format

### Advanced Features
- **Templates** - Pre-built rule sets for common project types
- **Merge** - Combine multiple rule files
- **Watch** - Auto-sync when rules change
- **Diff** - Compare rule files and generated configs
- **Lint** - Check for rule quality and best practices

### Configuration
```yaml
# .ai/cli-config.yaml
sync:
  auto_sync: true
  tools: ["cursor", "claude", "copilot"]
  
templates:
  directory: ".ai/templates"
  
validation:
  strict: false
  max_rules: 50
```

## Architecture

The CLI will be built with:
- **Node.js 22+** with TypeScript
- **Commander.js** for CLI framework
- **Ajv** for JSON Schema validation
- **Chalk** for colored output
- **Inquirer** for interactive prompts
- **Chokidar** for file watching

## Get Involved

We need developers to build this CLI:

- 🔧 **Node.js/TypeScript developers** - help build the core CLI
- 📝 **CLI UX designers** - design intuitive command interfaces
- 🧪 **Tool integrators** - implement sync for specific AI tools
- 📚 **Documentation writers** - create usage guides
- 🎨 **Template creators** - build rule templates for common use cases

## Technical Requirements

If you want to contribute:
- Experience with Node.js CLI tools
- TypeScript knowledge
- Understanding of YAML/JSON processing
- Familiarity with AI coding tools (preferred)

## Contributing

This is a key component of Universal AI Rules. Check out our [main project](../) for contribution guidelines and join us in building the future of AI-assisted development!

## License

MIT License - see [LICENSE](../LICENSE) for details.