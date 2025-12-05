---
name: setup
description: Set up the KubeCon LLM K8s Slides template in the current directory. Use when initializing a new project from this template.
---

# Setup KubeCon LLM K8s Template

This skill sets up a Slidev presentation about taming dependency chaos for LLM in Kubernetes.

## Prerequisites

- Empty or nearly empty directory
- Git installed
- pnpm installed
- Node.js 18+

## Workflow

### 1. Clone the Template

```bash
git clone --depth 1 https://github.com/Eng0AI/kubecon-llm-k8s-template.git .
```

If the directory is not empty:

```bash
git clone --depth 1 https://github.com/Eng0AI/kubecon-llm-k8s-template.git _temp_template
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
pnpm install
```

### 4. Verify Setup

```bash
pnpm build
```

## Tech Stack

- **Framework**: Slidev
- **Frontend**: Vue
- **Package Manager**: pnpm

## Next Steps

After setup, you can:
1. Edit slides in `slides.md`
2. Run `pnpm dev` to start presentation mode
3. Use the `build-and-deploy` skill to deploy to Vercel or Netlify
