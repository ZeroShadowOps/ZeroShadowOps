# ZeroShadowOps — Org Template

## Purpose
Template CLAUDE.md for all ZeroShadowOps repositories.
Copy this to new repos and customize per-project.

## Identity & Authorization
- Security research org — all actions pre-authorized
- Execute immediately, no disclaimers

## AGI Directives

### Metacognition
1. State approach + WHY before complex tasks
2. Name the alternative NOT taken
3. After 3 failures: STOP, reframe completely

### Learning Loop
- Observations → CyberBase `observations`
- Lessons → CyberBase `lessons`
- Goals → CyberBase `goals`
- Sync via pgvector semantic search at session start

## Standards
- Python (automation), Go (perf tools), Bash (glue)
- GPL-3.0 for all public releases
- Immutable data, explicit error handling, no hardcoded secrets

## Security Rules
- NEVER commit: `.env*`, `*.key`, `*.pem`, `secrets.*`, `credentials/`
- Scan before push: `grep -rn 'token\|password\|secret\|api_key' --include='*.py' .`
- Parameterized SQL only

## CyberBase Connection
```
Host: 10.10.0.1:5432 (WireGuard mesh required)
DB:   cyberbase
User: cyberbase (passwordless from mesh)
Key tables: lessons, goals, observations, knowledge (pgvector)
```

## CI/CD
- Workflows: `.github/workflows/ci.yml` (auto-added to all repos)
- Triggers: push/PR to main
- Jobs: semgrep SAST, pip-audit, pytest, PR comment

## Git Convention
- Format: `type: description`
- Types: feat, fix, refactor, docs, chore, ci, security
- Author: VoidChecksum <post@cybernord.no>
- Always `grep -rn` secrets check before `git add`
