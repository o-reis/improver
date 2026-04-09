# Filesystem Server

MCP server for reading and writing memory files.

## Installation

```bash
npm install -g @modelcontextprotocol/server-filesystem
```

## Configuration

```yaml
filesystem:
  enabled: true
  allowed_directories:
    - ./improver/memory
    - ./improver/patterns
    - ./improver/commands
```

## Usage

```
Tool: read_file
Input: { path: string }
Output: { content: string }

Tool: write_file
Input: { path: string, content: string }
Output: { success: boolean }

Tool: read_directory
Input: { path: string }
Output: { files: FileInfo[] }

Tool: search_files
Input: { directory: string, pattern: string }
Output: { matches: string[] }
```

## Security

- Restricted to allowed directories only
- No execution of files
- Read-only by default unless write enabled
