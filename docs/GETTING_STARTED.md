# Getting Started

This guide helps you set up your evaluation environment.

## Prerequisites

- Git installed
- Node.js installed (v18+)
- Claude Code installed

## Setup Steps

### 1. Clone the Repository

If you haven't already:

```bash
git clone [repo-url] atlas-eval
cd atlas-eval
```

### 2. Initialize Submodule

```bash
git submodule update --init
```

This pulls the atlas-workcore reference.

### 3. Configure Services (Optional)

If using Intent Service or Agent-Forge:

1. Copy `config/services.json`
2. Set environment variables:
   - `AGENT_FORGE_URL` - URL to Agent-Forge-Web
   - `SUPABASE_SERVICE_ROLE_KEY` - Auth key for Agent-Forge

For basic evaluation, these are optional.

### 4. Start a Session

Open your terminal and run:

```bash
claude
```

Then tell Claude what you want to build. That's it.

## What Happens During Sessions

You work on your project naturally. Claude helps using the Atlas system.

At the end of each session, you'll be asked for:
1. Three quick ratings (1-5 scale)
2. Any notes about friction or surprises
3. Which UI pages the work would map to

## If You Get Stuck

See `WHEN_STUCK.md` for troubleshooting.
