---
argument-hint: "<prompt>"
description: "Delegate a task to OpenAI Codex CLI"
allowed-tools: ["Bash", "Read", "AskUserQuestion"]
---

# Delegate to Codex

Run a task using OpenAI Codex CLI with the prompt: $ARGUMENTS

## 1. Select Model

Ask the user which model to use:

| Model | Best For |
|-------|----------|
| gpt-5.1-codex-max | Complex, long-running tasks (can run 24+ hours) |
| gpt-5.1-codex | Fast, balanced performance |
| gpt-5-codex-mini | Simple tasks, cost-efficient |

Default: `gpt-5.1-codex-max`

## 2. Select Sandbox Mode

Ask the user for sandbox mode:

| Mode | Description |
|------|-------------|
| read-only | Analysis only, no file changes |
| workspace-write | Can edit files in workspace |
| danger-full-access | Full network and system access |

Default: `read-only`

## 3. Run Codex

Assemble and execute the command:

```bash
codex exec --model <model> --sandbox <mode> --skip-git-repo-check "<prompt>" 2>/dev/null
```

## 4. Report Results

After execution completes:
- Show the output to the user
- Ask if they want to continue with a follow-up prompt
- For follow-ups, use: `echo "<follow-up>" | codex exec --skip-git-repo-check resume --last 2>/dev/null`

## Error Handling

- If Codex exits with non-zero code, report the error and ask user how to proceed
- If output contains warnings, inform the user and ask if adjustments are needed
- Always request confirmation before using `danger-full-access` mode
