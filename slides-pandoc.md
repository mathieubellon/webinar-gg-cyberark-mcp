---
title: "Tackling Secret & Vault Sprawl with AI"
subtitle: "GitGuardian + CyberArk MCP Servers in Action"
author: "A joint webinar — GitGuardian & CyberArk"
---

# Your Hosts Today

![Mathieu Bellon](mathieu-bellon.jpg){width=2in}
![Or Geisler](or-geisler.jpg){width=2in}
![Dwayne McDaniel](dwayne-mcdaniel.jpg){width=2in}

**Mathieu Bellon** — Product Manager, GitGuardian

**Or Geisler** — Software Engineer, CyberArk

**Dwayne McDaniel** — Dev Advocate, GitGuardian *(moderator)*

> *Questions? Drop them in the chat — we'll have a live Q&A at the end.*

---

# What We'll Cover Today

1. **Live Demo** — Watch AI detect secrets and vault them automatically
2. **Why We Built This** — The rise of NHIs, secret sprawl, and vault sprawl
3. **The Bigger Picture** — Identity-based workloads vs. enterprise reality
4. **How It Works** — GitGuardian & CyberArk MCP servers in action
5. **Q&A** — Your questions answered

---

# Live Demo

**What you'll see:**

- AI assistant detects hardcoded secrets in code
- GitGuardian MCP identifies secret type & risk
- CyberArk MCP vaults the secret automatically
- Code is refactored to use environment variables
- All in real-time, no context switching

> *This isn't science fiction. It's available today.*

---

# The Problem: Secret Sprawl

**Secrets are everywhere:**

- API keys in `.env` files
- Database credentials in config files
- Cloud access keys in CI/CD pipelines
- Service account tokens in scripts

**The reality:**

- 10+ million secrets exposed on GitHub **every year**
- Average company: **hundreds of repos**, thousands of secrets
- Developers context-switch between code, vault UI, docs

---

# The Problem: Vault Sprawl

**Vaults are multiplying:**

- AWS Secrets Manager
- Azure Key Vault
- Google Secret Manager
- HashiCorp Vault
- CyberArk Conjur
- Custom in-house solutions

**The challenge:**

- Which vault for which secret?
- What access policies apply?
- How to rotate credentials?
- How to track NHI lifecycle?

---

# Non-Human Identities (NHIs)

**NHIs outnumber humans 50:1 and growing:**

- Service accounts
- API keys
- Machine credentials
- Bot tokens
- CI/CD secrets
- Infrastructure access keys

**The governance gap:**

- **Humans:** SSO, MFA, role-based access, regular audits
- **NHIs:** Scattered secrets, unclear ownership, no rotation, no lifecycle tracking

---

# Why This Matters

**Security debt compounds:**

- Leaked secrets → data breaches
- Unrotated credentials → persistent access
- Unknown NHIs → shadow infrastructure
- Manual remediation → weeks of work

**The cost:**

- Average breach: **$4.45M** (IBM 2023)
- Time to detect exposed secret: **27 days** (GitGuardian)
- Time to remediate manually: **hours to days per secret**

---

# The Vision: Identity-Based Workloads

**The ideal world:**

- Every workload has a unique identity
- Credentials are automatically rotated
- Access is least-privilege by default
- Audits are automatic and real-time

**The reality:**

- Thousands of legacy secrets in code
- Dozens of vaults across the organization
- No single source of truth for NHIs
- Developers need to keep shipping features

---

# Enter: Model Context Protocol (MCP)

**What is MCP?**

- Open-source standard for AI assistant integration
- Created by Anthropic (Claude)
- Think "USB for AI" — one protocol, many capabilities

**Why it matters:**

- AI assistants can **read context** (code, repos, docs)
- AI assistants can **take actions** (scan, vault, remediate)
- AI assistants **orchestrate workflows** (detect → vault → refactor)

---

# MCP Architecture

**Three components:**

1. **MCP Host** (Claude, Cursor, Windsurf, Zed)
   - The AI assistant that orchestrates everything

2. **MCP Client** (built into the host)
   - Handles communication with MCP servers

3. **MCP Servers** (GitGuardian, CyberArk, etc.)
   - Expose capabilities as "tools" the AI can use

**The magic:** AI orchestrates multiple servers in a single workflow

---

# GitGuardian MCP Server

**Capabilities:**

- **Scan** — Detect 500+ secret types in code before commit
- **Remediate** — Get step-by-step fix instructions
- **Monitor** — Track incidents across all repos
- **Honeytoken** — Generate & hide canary tokens

**Use cases:**

- Pre-commit secret detection in your IDE
- AI-guided remediation during code review
- Automated secret audits across repos

---

# CyberArk Conjur MCP Server

**Capabilities:**

- **Vault Management** — Store secrets with proper policies
- **Secret Retrieval** — Fetch credentials programmatically
- **Access Control** — Enforce least-privilege policies
- **Audit Trail** — Track all secret access events

**Use cases:**

- Auto-vault detected secrets with correct policies
- Retrieve secrets for local dev/test
- Rotate credentials without manual work

---

# How It Works: Detection

**Step 1: AI scans code for secrets**

```python
# Before
DATABASE_URL = "postgresql://admin:MyP@ssw0rd@db.example.com/prod"
```

**Step 2: GitGuardian MCP identifies the secret**

- Type: PostgreSQL connection string
- Severity: High
- Location: `config.py:12`
- Recommendation: Vault + environment variable

---

# How It Works: Remediation

**Step 3: CyberArk MCP vaults the secret**

- Creates `prod/database/postgres_url` in Conjur
- Sets access policy: `prod-api-service` role
- Returns environment variable name: `DATABASE_URL`

**Step 4: AI refactors the code**

```python
# After
import os
DATABASE_URL = os.getenv("DATABASE_URL")
```

**Step 5: AI creates `.env.example`**

```bash
DATABASE_URL=postgresql://user:password@host/dbname
```

---

# Developer Experience

**Before MCP:**

1. Write code with hardcoded secret
2. Commit → CI fails → secret detected
3. Context switch to GitGuardian dashboard
4. Context switch to CyberArk vault UI
5. Manually vault the secret
6. Update code to use environment variable
7. Update CI/CD config
8. Commit again

**With MCP:**

1. Write code with hardcoded secret
2. AI detects → vaults → refactors
3. Review and commit

---

# Enterprise Reality

**The challenges:**

- **Scale:** Thousands of repos, millions of lines of code
- **Legacy:** Years of accumulated secrets in git history
- **Complexity:** Multiple vaults, inconsistent policies
- **Governance:** Who owns what? What needs rotation?

**What's needed:**

- **Find it** — Continuous detection across all code
- **Fix it** — Automated remediation at scale
- **Sustain it** — Lifecycle management for all NHIs

---

# Find It. Fix It. Sustain It.

**Find it.** Detect exposed secrets and risky patterns with GitGuardian's 500+ detectors — in your IDE, in CI/CD, across all repos.

**Fix it.** AI uses CyberArk Conjur MCP to vault secrets with the right policies, automatically. From detection to remediation in seconds — no context switching.

**Sustain it.** Make it continuous. Monitor for regressions, enforce rotation, track NHI lifecycle — even as teams, repos, and vaults scale across the enterprise.

> *One workflow. Two MCP servers. A secure-by-default developer experience.*

---

# Key Takeaways

1. **Secret & vault sprawl is real** — NHIs outnumber humans 50:1 and growing
2. **Find it** — GitGuardian detects secrets in your IDE, before they reach git
3. **Fix it** — CyberArk Conjur vaults them automatically via MCP, no context switching
4. **Sustain it** — continuous monitoring, rotation enforcement, and governance at scale
5. **MCP is the glue** — AI agents orchestrate both, so developers focus on code

---

# What's Next?

**Try it yourself:**

- GitGuardian MCP: [github.com/GitGuardian/ggtools-mcp-server](https://github.com/GitGuardian/ggtools-mcp-server)
- CyberArk Conjur MCP: [github.com/cyberark/conjur-mcp-server](https://github.com/cyberark/conjur-mcp-server)

**Resources:**

- MCP Specification: [modelcontextprotocol.io](https://modelcontextprotocol.io)
- GitGuardian Docs: [docs.gitguardian.com](https://docs.gitguardian.com)
- CyberArk Docs: [docs.cyberark.com](https://docs.cyberark.com)

---

# Questions?

**Drop your questions in the chat**

We're here to answer anything about:

- MCP architecture & integration
- GitGuardian secret detection
- CyberArk Conjur vaulting
- Enterprise deployment strategies
- Your specific use cases

> *Thank you for joining us today!*
