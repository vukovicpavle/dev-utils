# setex - Executable Permission Setter

Quickly sets executable permissions on files and copies them to `/usr/local/bin`.

## Features

- Automatically detects shell scripts in current directory
- Makes scripts executable (chmod +x)
- Installs scripts to /usr/local/bin
- Supports batch operations

## Usage

Inside the directory with scripts:

```bash
setex
```

### Interactive Usage

1. The script will scan the current directory for shell scripts
2. You'll see a prompt: "Type script number: "
3. Select either:
   - A specific script number
   - "all" to process all detected scripts

Each selected script will be:

- Made executable with chmod +x
- Copied to /usr/local/bin for system-wide access
