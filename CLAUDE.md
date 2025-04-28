# CLAUDE.md for Wilma CLI

This file contains information for Claude Code to help with working on this project.

## Project Overview

This project is a command-line interface for the Wilma school platform. It uses the `wilma` package as a dependency to provide the core API client functionality and adds a CLI layer with both regular and interactive modes.

## Project Structure

- `wilhelminacli/` - Main package
  - `__init__.py` - Package exports
  - `cli.py` - Command-line interface 
  - `tests/` - Test suite
    - `__init__.py`
    - `conftest.py` - Pytest configuration
    - `test_cli.py` - Tests for CLI
  - `utils/` - Utility functions
    - `__init__.py` - Utility exports
    - `interactive.py` - Interactive terminal UI
    - `summarizer.py` - AI message summarization

## Development Commands

Run these commands to verify your code before committing:

```bash
# Format with ruff
poetry run ruff format wilhelminacli

# Lint with ruff
poetry run ruff check wilhelminacli --fix

# Type check with mypy
poetry run mypy wilhelminacli

# Run tests
poetry run pytest
```

## CLI Commands

- `wilma login` - Test authentication
- `wilma messages` - List messages
- `wilma message <message_id>` - Show specific message content
- `wilma messages -i` - Interactive message browser
- `wilma messages --unread` - Show only unread messages
- `wilma messages-summarize` - Summarize unread messages with AI

## Interactive UI

The interactive UI uses the Textual framework to provide a terminal-based interface for browsing and reading messages. It has two main screens:

- `MessagesScreen` - Shows a list of messages
- `MessageDetailScreen` - Shows details of a selected message

## AI Summarization

The AI summarization feature uses Anthropic's Claude API to summarize messages. It requires an `ANTHROPIC_API_KEY` environment variable to be set.

## Common Issues and Solutions

- Authentication issues: Ensure correct credentials in the `.env` file or provide them as command-line arguments
- Anthropic API: Make sure to set the `ANTHROPIC_API_KEY` environment variable for message summarization
- Interactive mode: May require a terminal that supports ANSI escape sequences
