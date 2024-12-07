# Bash Utility Scripts

A collection of useful bash scripts for development workflow automation.

## Scripts Overview

### 1. `remote` - SSH Connection Manager

A utility for managing and connecting to SSH remotes.

**Features:**

- Connect to saved SSH connections
- Add new remote connections
- Remove existing connections
- Edit connection details
- Support for password and key-based authentication

**Usage:**

```bash
remote [command]
```

Configuration file format:

```
conn: connection_name
  addr: 1.1.1.1
  port: 22
  user: username
  pass: password
  pkey: private_key_file_name
  cert: certificate_file_name
```

### 2. `gcu` - Git Change User

Updates SSH identity file in your SSH config based on available SSH keys.

**Features:**

- Lists available SSH keys
- Updates SSH identity file in your SSH config

**Usage:**

```bash
gcu
```

### 3. `gitget` - Git Repository Branch Getter

A utility script for getting all git branches from a remote repository.

**Features:**

- Automatically fetches and pulls all remote branches

**Usage:**

Inside the repository directory:

```bash
gitget
```

### 4. `setex` - Executable Permission Setter

Quickly sets executable permissions on files and copies them to `/usr/local/bin`.

**Features:**

- Sets executable permissions (chmod +x)
- Copies files to `/usr/local/bin`
- Supports multiple files

**Usage:**

Inside the directory with scripts:

```bash
setex
```

## Installation

1. Clone this repository
2. Make scripts executable using by running `./setex`
