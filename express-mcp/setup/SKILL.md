---
name: setup
description: Set up the Express MCP Server template in the current directory. Use when initializing a new project from this template.
---

# Setup Express MCP Server Template

This skill sets up an MCP server implementation with Express.js and TypeScript.

## Prerequisites

- Empty or nearly empty directory
- Git installed
- npm installed
- Node.js 18+

## Workflow

### 1. Clone the Template

```bash
git clone --depth 1 https://github.com/Eng0AI/express-mcp.git .
```

If the directory is not empty:

```bash
git clone --depth 1 https://github.com/Eng0AI/express-mcp.git _temp_template
mv _temp_template/* _temp_template/.* . 2>/dev/null || true
rm -rf _temp_template
```

### 2. Remove Git History (Optional)

```bash
rm -rf .git
git init
```

### 3. Install Dependencies

```bash
npm install
```

### 4. Verify Setup

```bash
npm run build
```

## Tech Stack

- **Framework**: Express.js
- **Language**: TypeScript
- **Protocol**: MCP (Model Context Protocol)
- **Package Manager**: npm
