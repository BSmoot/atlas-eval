# Getting Started

This guide helps you set up your evaluation environment.

## Prerequisites

**Required:**
- Git installed
- Claude Code CLI installed

**Optional (for TypeScript runtime):**
- Node.js v18+
- The `intent/intent-identity` repo (see below)

## Setup Steps

### 1. Clone the Repository

```bash
git clone https://github.com/BSmoot/atlas-eval.git
cd atlas-eval
```

### 2. Initialize Submodule

```bash
git submodule update --init --recursive
```

This pulls the atlas-workcore reference (documentation and platform specs).

### 3. (Optional) TypeScript Runtime Dependencies

The `atlas-workcore/atlas-core` TypeScript code depends on `@intent/identity-agent`. If you need to run the TypeScript components directly:

```bash
# Clone as sibling directory
cd ..
git clone [intent-repo-url] intent
cd atlas-eval
```

**For basic CLI evaluation, this is NOT required.** The evaluation runs through Claude Code, which doesn't need the TypeScript runtime.

### 4. (Optional) Configure External Services

If using Intent Service or Agent-Forge for M2M testing:

1. Edit `config/services.json`
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
