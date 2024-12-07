# remote - SSH Connection Manager

A utility for managing and connecting to SSH remotes.

## Features

- Connect to saved SSH connections
- Add new remote connections
- Remove existing connections
- Edit connection details
- Support for password and key-based authentication

## Usage

```bash
remote [command]
```

## Configuration

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
