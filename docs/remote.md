# remote - SSH Connection Manager

A command-line tool to manage and connect to SSH remotes.

## Features

- Connect to saved SSH connections
- Add new remote connections
- Remove existing connections
- Edit connection details
- Support for password and key-based authentication
- Initialize SSH configuration directory and files
- Test connections without connecting
- Search through saved connections
- Backup configuration to timestamped files

## Usage

```bash
remote [command]
```

### Basic Commands

- `init` - Initialize remote configuration (creates ~/.ssh directory and remotes file)
- `go`, `connect` - Connect to a saved remote
- `add` - Add a new remote connection
- `remove`, `rm` - Remove an existing connection
- `edit` - Edit connection details
- `list`, `ls` - List all connection names
- `help` - Show help message (default)

### Advanced Commands

- `backup` - Create a timestamped backup of your remotes file
- `test` - Test connection to a remote without actually connecting
- `search` - Search through remotes by name, address, or username
- `import` - Import remotes from another file (coming soon)

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

### Examples

List available connections:

```bash
$ remote list
Available connections:
myserver
development
staging
```

Test a connection:

```bash
$ remote test
Select a connection to test:
1) myserver
2) development
3) staging
#? 1
Testing connection to myserver...
✅ Connection successful!
```

Search for connections:

```bash
$ remote search
Enter search term: dev
Matching connections:
conn: development
```

Create a backup:

```bash
$ remote backup
Backup created at: ~/.ssh/remotes_backup_20240101_120000
```
