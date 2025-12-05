---
name: setup
description: Set up the Go Clean Architecture template in the current directory. Use when initializing a new project from this template.
---

# Setup Go Clean Architecture Template

This skill sets up a Go backend with Gin, MongoDB, JWT, and Docker.

## Prerequisites

- Empty or nearly empty directory
- Git installed
- Go 1.21+
- MongoDB
- Docker (optional)

## Workflow

### 1. Clone the Template

```bash
git clone --depth 1 https://github.com/amitshekhariitbhu/go-backend-clean-architecture.git .
```

If the directory is not empty:

```bash
git clone --depth 1 https://github.com/amitshekhariitbhu/go-backend-clean-architecture.git _temp_template
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
go mod download
```

### 4. Setup Environment

Configure MongoDB connection and JWT secret.

### 5. Build

```bash
go build -o app ./cmd/main.go
```

## Tech Stack

- **Framework**: Gin
- **Language**: Go
- **Database**: MongoDB
- **Auth**: JWT
- **Architecture**: Clean Architecture
