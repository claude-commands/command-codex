# command-codex

A Claude Code slash command for delegating tasks to OpenAI Codex CLI.

## Installation

```bash
git clone git@github.com:claude-commands/command-codex.git ~/projects/claude-commands/command-codex
ln -s ~/projects/claude-commands/command-codex/codex.md ~/.claude/commands/codex.md
```

## Usage

```
/codex analyze this codebase for security vulnerabilities
```

## Models (Nov 2025)

| Model | Best For |
|-------|----------|
| `gpt-5.1-codex-max` | Complex, long-running tasks (can run 24+ hours) |
| `gpt-5.1-codex` | Fast, balanced performance |
| `gpt-5-codex-mini` | Simple tasks, cost-efficient |

## Reasoning Levels

| Level | Use Case |
|-------|----------|
| `low` | Quick responses |
| `medium` | Daily driver (default) |
| `high` | Complex problems |
| `xhigh` | Maximum thinking |

## Sandbox Modes

| Mode | Description |
|------|-------------|
| `read-only` | Analysis only (default) |
| `workspace-write` | Can edit files |
| `danger-full-access` | Full system access |

## Requirements

- [Codex CLI](https://github.com/openai/codex) installed
- OpenAI API access

## Updates

```bash
cd ~/projects/claude-commands/command-codex && git pull
```
