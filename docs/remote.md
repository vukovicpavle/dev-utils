# remote - SSH Connection Manager

A utility for managing and connecting to SSH remotes.

## Features

- Connect to saved SSH connections
- Add new remote connections
- Remove existing connections
- Edit connection details
- Support for password and key-based authentication
- Initialize SSH configuration directory and files

## Usage

```bash
remote [command]
```

### Commands

- `init` - Initialize remote configuration (creates ~/.ssh directory and remotes file)
- `go`, `connect` - Connect to a saved remote
- `add` - Add a new remote connection
- `remove`, `rm` - Remove an existing connection
- `edit` - Edit connection details
- `list`, `ls` - List all saved connections
- `help` - Show help message (default)

## Configuration

The utility stores configurations in `~/.ssh/remotes` with permissions set to 600 (user read/write only).

Configuration file format:

```
conn: connection_name
  addr: 1.1.1.1
  port: 22
  user: username
  pass: password
  pkey: private_key_file_name
```

### Initialization

Running `remote init` will:

1. Create the ~/.ssh directory if it doesn't exist (with 700 permissions)
2. Create the remotes configuration file if it doesn't exist (with 600 permissions)

This ensures proper security permissions for SSH-related files.
