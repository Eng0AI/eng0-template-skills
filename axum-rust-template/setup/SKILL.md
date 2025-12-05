---
name: setup
description: Set up the Axum Rust API template in the current directory. Use when initializing a new project from this template.
---

# Setup Axum Rust API Template

This skill sets up a Rust Axum API with Diesel ORM and DDD architecture.

## Prerequisites

- Empty or nearly empty directory
- Git installed
- Rust toolchain installed
- PostgreSQL (for Diesel)

## Workflow

### 1. Clone the Template

```bash
git clone --depth 1 https://github.com/Eng0AI/axum-rust-template.git .
```

If the directory is not empty:

```bash
git clone --depth 1 https://github.com/Eng0AI/axum-rust-template.git _temp_template
mv _temp_template/* _temp_template/.* . 2>/dev/null || true
rm -rf _temp_template
```

### 2. Remove Git History (Optional)

```bash
rm -rf .git
git init
```

### 3. Build Project

```bash
cargo build
```

### 4. Setup Database

Configure database and run Diesel migrations.

## Tech Stack

- **Framework**: Axum
- **Language**: Rust
- **ORM**: Diesel
- **Architecture**: DDD
