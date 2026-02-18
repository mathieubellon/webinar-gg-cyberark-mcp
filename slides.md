---
marp: true
theme: default
paginate: true
footer: '<span class="footer-left"><img src="gg-logo.svg" class="footer-logo" alt="" /> GitGuardian</span><span class="footer-right">Confidential</span>'
style: |
  @import url('https://fonts.googleapis.com/css2?family=Funnel+Display:wght@300..800&family=Instrument+Sans:ital,wght@0,400..700;1,400..700&display=swap');

  :root {
    --bg: #000;
    --fg: #fff;
    --fg-secondary: #c8cada;
    --muted: #7a7e98;
    --accent: #4E73DB;
    --accent-light: #9FA8EA;
    --accent-soft: #C0C4F2;
    --accent-hover: #295ABE;
    --accent-dark: #0C2860;
    --accent-surface: #E0E1F9;
    --code-bg: #0a0e1a;
    --table-border: #1a2040;
  }

  section {
    font-family: 'Instrument Sans', sans-serif;
    background-color: var(--bg);
    color: var(--fg);
    padding: 50px 80px 120px 80px;
    justify-content: flex-start;
    font-size: 26px;
    line-height: 1.6;
  }

  section::after {
    color: var(--muted);
    font-size: 0.7em;
    font-family: 'Instrument Sans', sans-serif;
  }

  /* Footer */
  section footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: calc(100% - 160px);
    left: 80px;
    bottom: 30px;
    padding-top: 14px;
    border-top: 2px solid var(--accent);
    font-family: 'Instrument Sans', sans-serif;
    font-size: 0.6em;
    color: var(--muted);
  }

  section footer .footer-left {
    display: flex;
    align-items: center;
    gap: 8px;
    color: var(--fg);
    font-weight: 600;
    letter-spacing: 0.02em;
  }

  section footer .footer-logo {
    height: 22px;
    width: auto;
    vertical-align: middle;
  }

  section footer .footer-right {
    color: var(--muted);
    font-weight: 400;
  }

  /* Headings — Funnel Display only */
  h1 {
    font-family: 'Funnel Display', sans-serif;
    color: var(--fg);
    font-weight: 800;
    font-size: 2.1em;
    margin-bottom: 0.4em;
    letter-spacing: -0.01em;
    line-height: 1.15;
  }

  h2 {
    font-family: 'Funnel Display', sans-serif;
    color: var(--fg);
    font-weight: 400;
    font-size: 1.3em;
    margin-top: 0;
    line-height: 1.3;
  }

  h3 {
    font-family: 'Funnel Display', sans-serif;
    color: var(--fg);
    font-weight: 500;
    font-size: 1.05em;
    margin-top: 0.5em;
    line-height: 1.3;
  }

  /* Bold — white, not colored (accessibility guideline) */
  strong {
    color: var(--fg);
    font-weight: 700;
  }

  /* Emphasis = section label */
  em {
    color: var(--muted);
    font-style: italic;
    font-size: 0.85em;
  }

  /* Links */
  a {
    color: var(--accent-light);
    text-decoration: none;
  }

  a:hover {
    text-decoration: underline;
  }

  /* Lists */
  ul, ol {
    margin-top: 0.3em;
  }

  li {
    margin-bottom: 0.35em;
    line-height: 1.55;
    color: var(--fg-secondary);
  }

  li strong {
    color: var(--fg);
  }

  li::marker {
    color: var(--accent);
  }

  /* Paragraphs */
  p {
    line-height: 1.6;
    margin-top: 0.4em;
    margin-bottom: 0.4em;
    color: var(--fg-secondary);
  }

  /* Code blocks */
  code {
    background: var(--code-bg);
    color: var(--accent-light);
    padding: 2px 8px;
    border-radius: 4px;
    font-size: 0.82em;
    font-family: 'SF Mono', 'Fira Code', 'Cascadia Code', monospace;
    border: 1px solid var(--table-border);
  }

  pre {
    background: var(--code-bg) !important;
    border: 1px solid var(--table-border);
    border-radius: 8px;
    padding: 18px !important;
    margin: 0.6em 0;
  }

  pre code {
    color: var(--fg-secondary);
    background: transparent;
    padding: 0;
    font-size: 0.72em;
    line-height: 1.6;
    border: none;
  }

  /* Tables — force override Marp default theme */
  section table {
    font-size: 0.72em;
    border-collapse: collapse;
    width: 100%;
    margin: 0.5em 0;
    font-family: 'Instrument Sans', sans-serif;
    border: none !important;
  }

  section table thead th {
    background: var(--accent-dark) !important;
    color: var(--fg) !important;
    font-weight: 600;
    text-align: left;
    padding: 8px 14px;
    border: none !important;
    border-bottom: 2px solid var(--accent) !important;
  }

  section table tbody td {
    padding: 8px 14px;
    border: none !important;
    border-bottom: 1px solid var(--table-border) !important;
    color: var(--fg-secondary) !important;
    background: var(--bg) !important;
  }

  section table tbody td strong {
    color: var(--fg) !important;
  }

  section table tbody tr:nth-child(even) td {
    background: #060a14 !important;
  }

  /* Blockquotes */
  blockquote {
    border-left: 3px solid var(--accent);
    padding-left: 20px;
    margin: 0.8em 0;
    font-size: 0.9em;
  }

  blockquote p {
    color: var(--muted);
    font-style: italic;
  }

  blockquote strong {
    color: var(--fg-secondary);
  }

  /* Title slide */
  section.title {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding-bottom: 120px;
  }

  section.title h1 {
    font-size: 2.6em;
    font-weight: 800;
    margin-bottom: 0.2em;
  }

  section.title h2 {
    font-size: 1.1em;
    font-weight: 400;
    color: var(--fg-secondary);
    margin-top: 0;
    font-family: 'Instrument Sans', sans-serif;
  }

  section.title p {
    color: var(--muted);
    font-size: 0.75em;
    margin-top: 1.5em;
    font-style: italic;
  }

  section.title ol, section.title li {
    text-align: left;
    color: var(--fg-secondary);
  }

  section.title li strong {
    color: var(--fg);
  }

  /* Section divider slides */
  section.divider {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding-bottom: 120px;
  }

  section.divider h1 {
    font-size: 2.4em;
    font-weight: 800;
    margin-bottom: 0.2em;
  }

  section.divider h2 {
    font-weight: 300;
    color: var(--fg-secondary);
    font-size: 1.2em;
    font-family: 'Instrument Sans', sans-serif;
  }

  section.divider h3 {
    font-weight: 300;
    color: var(--muted);
    font-size: 0.95em;
    font-family: 'Instrument Sans', sans-serif;
  }

---

<!-- _class: title -->

# MCP & GitGuardian

## How MCP works and why it matters for agents & developers

*This document is for informational purposes only*

---

<!-- _class: divider -->

# Part 1

## What is MCP and how does it work?

---

*The problem*

# Fragmented Integrations

Today's AI assistants are **isolated from the outside world**.

Each integration requires a **custom, one-off connector**:

- Different APIs, different auth, different data formats
- Every new tool = new code to write and maintain
- **N agents x M tools = N x M integrations**

> *"Before MCP, connecting AI to external tools felt like the early days of phone chargers — every vendor had their own plug."*

---

*The solution*

# Enter MCP: A USB-C Port for AI

**Model Context Protocol** is an open standard introduced by Anthropic (Nov 2024).

It provides a **single, universal interface** between AI applications and external systems.

| Before MCP | With MCP |
|---|---|
| Custom connector per tool | **One standard protocol** |
| Tight coupling | **Loose coupling** |
| Hard to scale | **Plug-and-play** |
| Vendor lock-in | **Open ecosystem** |

MCP is now maintained by the **Linux Foundation** (Agentic AI Foundation).

---

*Architecture*

# MCP Architecture

A clean **client-server** model:

```
┌──────────────────┐          ┌──────────────────┐
│   MCP Client     │  JSON-RPC│   MCP Server      │
│ (AI App / Agent) │◄────────►│ (Tool / Service)  │
│                  │   2.0    │                    │
│  Claude, Cursor, │          │  GitHub, Slack,    │
│  Windsurf, etc.  │          │  DB, GitGuardian…  │
└──────────────────┘          └──────────────────┘
```

- **MCP Client** — The AI-powered application (IDE, chatbot, agent)
- **MCP Server** — Exposes capabilities from an external system
- **Transport** — JSON-RPC 2.0, lightweight and language-agnostic

---

*Primitives*

# What Can an MCP Server Expose?

MCP servers offer three primitives to clients:

| Primitive | Description | Example |
|---|---|---|
| **Tools** | Functions the agent can call | `scan_secrets`, `create_issue` |
| **Resources** | Data the agent can read | Files, DB records, API docs |
| **Prompts** | Reusable prompt templates | "Summarize this PR", "Triage bug" |

The agent **discovers** available tools at runtime — no hardcoding needed.

---

*Flow*

# How an MCP Interaction Works

```
1.  Agent connects to MCP server
2.  Server advertises its tools (name, description, schema)
3.  User asks: "Scan my code for secrets"
4.  Agent picks the right tool → scan_secrets
5.  Agent calls the tool via JSON-RPC
6.  Server executes and returns results
7.  Agent interprets results and responds to user
```

The key insight: **the agent decides which tool to use** based on the user's intent and the tool descriptions.

---

<!-- _class: divider -->

# Why MCP Matters

## For agents and developers alike

---

*For agents*

# Why MCP Matters for Agents

- **Dynamic tool discovery** — agents learn what's available at runtime
- **Standardized interface** — one protocol to interact with any service
- **Composability** — chain multiple MCP servers in a single workflow
- **Scalability** — add new capabilities without changing agent code
- **Context awareness** — agents get richer context from external systems

> *An agent with MCP can go from "I can only chat" to "I can read your DB, file issues, scan code, deploy services" — all through the same protocol.*

---

*For developers*

# Why MCP Matters for Developers

- **Write once, use everywhere** — build an MCP server, any MCP client can use it
- **Stay in your IDE** — tools come to you, not the other way around
- **Reduced context switching** — no need to leave Cursor to check dashboards
- **Community ecosystem** — thousands of open-source MCP servers available
- **Easy to build** — SDKs in Python, TypeScript, Java, Go, Rust, C#

```bash
# Use any MCP server from your IDE with zero custom code
npx @anthropic/mcp-server-github   # GitHub integration
npx @gitguardian/mcp-server        # Security scanning
```

---

*Ecosystem*

# The MCP Ecosystem Today

**Adoption has been massive** since the Nov 2024 launch:

- **Anthropic** — native support in Claude
- **OpenAI** — adopted MCP in their agents
- **Google DeepMind** — integrated MCP support
- **Cursor, Windsurf, Zed** — IDE-level integration
- **1000s of community servers** — GitHub, Slack, DBs, monitoring, security

MCP is becoming the **de facto standard** for agent-tool communication.

---

<!-- _class: divider -->

# Part 2

## GitGuardian MCP Server

### Real-time secrets security in your development workflow

---

*The problem*

# Secrets in Code

Hardcoded secrets are **one of the most common security vulnerabilities**:

- API keys, tokens, passwords committed to repos
- Detected **too late** — often after push
- Traditional scanners run in CI/CD — **feedback loop is slow**
- Developers must context-switch to security dashboards

> **70%+** *of leaked secrets remain valid and exploitable days after exposure.*

What if your AI coding assistant could catch secrets **before you commit**?

---

*Overview*

# GitGuardian MCP Server

Launched **July 2025** — **real-time secrets detection directly into your IDE**.

Works inside **Cursor**, **Windsurf**, and **Zed** — wherever your agent lives.

| Tool | What it does |
|---|---|
| `scan_secrets` | Proactively scan code for **500+ secret types** |
| `list_incidents` | View existing secret incidents in your repo |
| `remediate_secret_incidents` | Guided remediation with **best practices** |
| `generate_honey_tokens` | Create and hide honeytokens for **breach detection** |

---

*In practice*

# Proactive Scanning — `scan_secrets`

You write code, your agent **automatically detects secrets** before commit:

```
Developer: "Review this file before I commit"

Agent: ⚠️  I found a hardcoded AWS access key on line 42.
       Let me help you move it to an environment variable.

       → Created .env with AWS_ACCESS_KEY placeholder
       → Updated code to use os.environ["AWS_ACCESS_KEY"]
       → Added .env to .gitignore
```

The security feedback loop goes from **hours to seconds**.

---

*In practice*

# Incident Management — `list_incidents`

Query existing secret incidents without leaving your IDE:

```
Developer: "Are there any secret incidents in this repo?"

Agent: I found 3 open incidents:

       1. AWS Secret Key in config/settings.py (line 15)
          → Assigned to you, opened 2 days ago
       2. Slack Webhook URL in deploy.sh (line 8)
          → Unassigned, opened 1 week ago
       3. GitHub PAT in .env.production (line 3)
          → Assigned to @teammate, opened 3 days ago
```

---

*In practice*

# Guided Remediation — `remediate_secret_incidents`

Step-by-step fix with **best practices** for each secret type:

```
Developer: "Help me fix the AWS key leak"

Agent: Here's the remediation plan:

       1. ✅ Rotate the AWS access key in IAM console
       2. ✅ Replace hardcoded value with env variable
       3. ✅ Create .env.example with placeholder
       4. ✅ Update .gitignore to exclude .env
       5. 🔧 Optional: git commands to clean history
```

Contextual advice — **not generic warnings**.

---

*In practice*

# Honeytokens — `generate_honey_tokens`

Plant **decoy credentials** in your codebase to detect intrusions:

```
Developer: "Add a honeytoken to this config file"

Agent: Done! I've hidden a GitGuardian honeytoken in
       config/database.yml.

       If anyone tries to use this credential,
       GitGuardian will alert you immediately.

       → Early breach detection
       → Zero false positives (only triggered on actual use)
```

---

<!-- _class: divider -->

# Why GitGuardian MCP?

---

*Shift-left security*

# Why It Matters for Developers

| Traditional Approach | With GitGuardian MCP |
|---|---|
| Secrets found in CI/CD | Secrets found **while coding** |
| Context switch to dashboard | Stay **in your IDE** |
| Manual remediation | **AI-guided** fix with best practices |
| Reactive detection | **Proactive** scanning before commit |
| Hours to remediate | **Seconds** to remediate |

---

*Design principles*

# Built for Security

The GitGuardian MCP Server is built with security in mind:

- **Read-only by design** — minimizes risk, no destructive actions
- **Safe and supervised** — agent behavior is auditable
- **500+ detectors** — covers all major secret types
- **Works with your stack** — language and framework agnostic
- **Open source** — available at [github.com/GitGuardian/gg-mcp](https://github.com/GitGuardian/gg-mcp)

> *"A new security primitive — proactive, context-aware security actions directly in the development environment."*
> *— Eric Fourrier, CEO GitGuardian*

---

*Getting started*

# Get Started in 2 Minutes

### 1. Add to your MCP configuration

```json
{
  "mcpServers": {
    "gitguardian": {
      "command": "pipx",
      "args": ["run", "ggshield", "mcp"]
    }
  }
}
```

### 2. Start using it

Just ask your agent: *"Scan this file for secrets"* — it handles the rest.

---

<!-- _class: title -->

# Key Takeaways

1. **MCP is the universal standard** for connecting AI agents to tools
2. **Agents become more capable** when they can discover and use tools dynamically
3. **GitGuardian MCP** brings secrets security **into the developer workflow**
4. **Shift-left security** — catch secrets before they leak, not after

---

<!-- _class: title -->

# Thank You

## Questions?

[modelcontextprotocol.io](https://modelcontextprotocol.io) · [github.com/GitGuardian/gg-mcp](https://github.com/GitGuardian/gg-mcp) · [gitguardian.com](https://gitguardian.com)
