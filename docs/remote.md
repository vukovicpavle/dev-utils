# remote - SSH Connection Manager

A command-line tool to manage and connect to SSH remotes.

## Features

- 🔌 Connect to saved SSH remotes
- ➕ Add new remote connections
- 🗑️ Remove existing remotes
- ✏️ Edit remote configurations
- 🔍 Test remote connections
- 💾 Backup remote configurations
- 🔎 Search through remotes

## Usage

```bash
remote [command]
```

### Commands

- `init` - Initialize remote configuration
- `go`, `connect` - Connect to a remote
- `add` - Add a new remote
- `remove`, `rm` - Remove a remote
- `edit` - Edit an existing remote
- `list`, `ls` - List all remotes
- `backup` - Backup remotes to timestamped file
- `test` - Test connection to a remote
- `search` - Search through remotes
- `help` - Show help message (default)

## Examples

List available connections:

```bash
$ remote list
📋 Available connections:
------------------------
  myserver
  development
  staging
```

Connect to a remote:

```bash
$ remote connect
🔌 Select a connection:
-------------------
1) myserver
2) development
3) staging
#? 1
📡 Connection details:
   Command: ssh user@myserver.com -p 22
🚀 Connect now? (y/n): y
   Connecting...
```

Add a new remote:

```bash
$ remote add
➕ Add new connection
------------------
   Name: production
   Address: prod.server.com
   Port (default: 22): 2222
   Username: admin
   Password (optional):
   Private key filename (optional): prod_key
✅ Remote 'production' added successfully!
```

Test a connection:

```bash
$ remote test
🔍 Select a connection to test:
----------------------------
1) myserver
2) development
#? 1
🔄 Testing connection to myserver...
   user@myserver.com:22
✅ Connection successful!
```

Search for connections:

```bash
$ remote search
🔎 Enter search term: dev
📍 Matching connections:
---------------------
  conn: development
```

Create a backup:

```bash
$ remote backup
💾 Backup created successfully!
   Location: ~/.ssh/remotes_backup_20240101_120000
```

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

```bash
$ remote init
📁 Created SSH directory: ~/.ssh
📄 Created connections file: ~/.ssh/remotes
```

This ensures proper security permissions for SSH-related files.
