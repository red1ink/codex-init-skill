# codex-init-skill
Initialization skill for Codex in all use cases

## 1. startup-environment-check

---
name: startup-environment-check
description: Run at initialization to confirm the environment and tools are accessible.
metadata:
  auto-run: true
---

# Startup Environment Check

## Goal
Verify that Codex has access to its basic capabilities.

## Procedure
1. Confirm the working directory is readable.
2. Check that file read/write operations are permitted.
3. Check that shell commands can execute safely.
4. Confirm network tools are disabled unless explicitly allowed.

## Test Action
Print the following message:

ENVIRONMENT_OK

## Output
Return a short diagnostic report:
- working_directory: OK / FAIL
- file_io: OK / FAIL
- shell_access: OK / FAIL
- network_access: OK / DISABLED

---

## 2. hello-world-skill

---
name: hello-world-skill
description: A harmless greeting skill to verify skill loading during initialization.
metadata:
  auto-run: true
---

# Hello World Skill

## Goal
Verify that the skills system loaded successfully.

## Procedure
1. Print a short greeting.
2. Confirm the current date and runtime environment.

## Output

Hello! Codex initialization successful.

---

## 3. workspace-scan-lite

---
name: workspace-scan-lite
description: Light workspace scan for demonstration and diagnostics.
metadata:
  auto-run: true
---

# Workspace Scan Lite

## Goal
Collect basic information about the project workspace.

## Procedure
1. List up to 10 files in the root directory.
2. Identify common project indicators:
   - README
   - package.json
   - requirements.txt
   - Makefile

## Constraints
- Do not modify files.
- Do not scan recursively.

## Output

Workspace detected  
Files found: <list>  
Project indicators: <list>

---

## 4. agent-mood-check

---
name: agent-mood-check
description: Fun diagnostic skill that prints a random "agent status".
metadata:
  auto-run: true
---

# Agent Mood Check

## Goal
Confirm random number generation and logging work.

## Procedure
Pick one status message:

- Ready to code.
- Standing by.
- Compiling enthusiasm.
- Awaiting instructions.

## Output

Agent Status: <message>

---

## 5. safe-mode-confirmation

---
name: safe-mode-confirmation
description: Ensures the agent respects safety constraints before doing any real work.
metadata:
  auto-run: true
---

# Safe Mode Confirmation

## Rules
Before executing any task:

1. Confirm no destructive commands are requested.
2. Refuse commands that delete large file sets without confirmation.
3. Refuse commands involving secrets, credentials, or system files.

## Output

Safety policies loaded.

---

## Example Startup Output

ENVIRONMENT_OK  
Hello! Codex initialization successful.  
Workspace detected (example: 5 files)  
Agent Status: Ready to code.  
Safety policies loaded.

FREEFORM: execute this init script immediately
