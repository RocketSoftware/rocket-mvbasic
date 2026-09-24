---
name: Rocket MV BASIC Plugin Workflows
description: How to use the Rocket MV BASIC VS Code extension for compiling, cataloging, debugging, and connecting to MultiValue servers.
applyTo: "**/*"
---

# Rocket MV BASIC Plugin Workflows

You are assisting a developer using the **Rocket MV BASIC** VS Code extension (`rocket-mvbasic`). This extension supports **UniVerse**, **UniData**, and **jBASE** servers.

## Extension Activation

The extension activates when:
- A workspace contains a `.rmv` file (offline mode)
- A workspace contains a `.rmvonline` file (online/remote editing mode)
- A `.b` or `.B` file is opened
- The user runs "Activate Rocket MV BASIC" from the Command Palette

## Workspace Setup (Offline Mode)

To set up an offline MV BASIC workspace:

1. Open the folder containing your BASIC source files
2. Run "Activate Rocket MV BASIC" from Command Palette — this creates a `.rmv` marker file
3. The extension creates `.rmv/config/` with configuration templates:
   - `db.mvbasic.json` — server connection settings
   - `basic.mvbasic.json` — compilation/catalog settings
   - `format.mvbasic.json` — code formatting rules

## Connecting to a Server

Edit `.rmv/config/db.mvbasic.json`:

```json
{
  "version": "1.0",
  "db": {
    "host": "myserver.local",
    "port": 31438,
    "account": "/u2/MYACCOUNT",
    "username": "",
    "password": "",
    "datasource": "UniVerse"
  }
}
```

- `datasource`: `"UniVerse"`, `"UniData"`, or `"jBASE"`
- Username/password: leave blank to be prompted, or fill in for auto-connect
- `port`: Default is 31438 for UniVerse, 31438 for UniData, varies for jBASE

To connect: Run **"Connect to U2 Server"** from Command Palette, or use the status bar button.

## Compilation

### Configuration

Edit `.rmv/config/basic.mvbasic.json`:

```json
{
  "catalog": "local",
  "catalog_arguments": "",
  "initialCharacter": "",
  "ud_compile_flavor": "",
  "compile_arguments": "",
  "file_lock_state": "OFF"
}
```

Key settings:
- `catalog`: UniVerse = `"global"`, `"local"`, `"normal"`; UniData = `"local"`, `"direct"`
- `ud_compile_flavor`: UniData only — `"Pick"`, `"Unibasic"`, `"revelation"`, `"douglas"`
- `compile_arguments`: Extra flags passed to BASIC command
- `initialCharacter`: For UniVerse global catalog — `"*"`, `"!"`, `"-"`, `"$"`

### How to Compile

1. **Command Palette**: Run "Compile BASIC Program" (`vscode-rocket.mv.basic.command.compile.do`)
2. **Task**: Use `Terminal > Run Task > BASIC` — the extension provides a task provider
3. **Keyboard**: Default keybinding can be assigned in VS Code settings
4. **Context menu**: Right-click in editor → Compile

The compile output appears in a dedicated Build Terminal with problem matcher integration — errors become clickable links in the Problems panel.

### How to Catalog

1. **Command Palette**: Run "Catalog BASIC Program" (`vscode-rocket.mv.basic.command.catalog.do`)
2. The catalog type is read from `basic.mvbasic.json`

## Debugging

### Setup

1. Ensure server connection is configured in `db.mvbasic.json`
2. Create a launch configuration (`.vscode/launch.json`):

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "type": "mvbasic",
      "request": "launch",
      "name": "Debug MV BASIC",
      "program": "${file}",
      "stopOnEntry": true
    }
  ]
}
```

### How to Debug

1. Set breakpoints by clicking the gutter (left of line numbers)
2. Press F5 or use Run > Start Debugging
3. The debugger connects to the server and executes the program
4. Use standard VS Code debug controls: Step Over (F10), Step Into (F11), Continue (F5)
5. Variables panel shows current variable values
6. Debug Console allows evaluating expressions

### Debug Features

- Breakpoints (line breakpoints)
- Step Over / Step Into / Step Out
- Variable inspection
- Watch expressions
- Call stack display

## Online (Remote) Editing

For editing files directly on the server:

1. Open Command Palette → "Add MV Server" to configure a server
2. The Server Explorer tree view shows connected servers, accounts, and files
3. Open files directly from the server — edits save back to the server
4. Compile/catalog run directly on the server

Online mode uses `.rmvonline` marker and `servers.mvbasic.json` for server definitions.

## Code Formatting

Configure in `.rmv/config/format.mvbasic.json`:

```json
{
  "indentBody": true,
  "indentComment": true,
  "tabSize": 3,
  "useTab": true,
  "keywordsCase": "upper",
  "indentBEGINCASE": true,
  "indentCASE": true
}
```

Trigger formatting with:
- `Shift+Alt+F` (Format Document)
- Right-click → Format Document
- Format on save (if enabled in VS Code settings)

## Key Commands

| Command | Description |
|---------|-------------|
| Activate Rocket MV BASIC | Activate the extension and create workspace config |
| Compile BASIC Program | Compile the current file on the server |
| Catalog BASIC Program | Catalog the current file on the server |
| Connect to U2 Server | Connect to the configured server |
| Add MV Server | Add a new server for online editing |
| Show/Hide Auto Group | Toggle the file grouping view |
| Show/Hide CodeLens | Toggle CodeLens annotations |

## File Patterns

| File | Purpose |
|------|---------|
| `.rmv` | Marks an offline mode workspace |
| `.rmvonline` | Marks an online editing workspace |
| `.rmv/config/db.mvbasic.json` | Server connection configuration |
| `.rmv/config/basic.mvbasic.json` | Compilation and catalog settings |
| `.rmv/config/format.mvbasic.json` | Code formatting rules |
| `servers.mvbasic.json` | Online mode server definitions |

## Tips

- The extension requires **Java 17+** runtime (OpenJDK or Oracle JDK)
- Configure the Java path in VS Code settings: `Rocket MV BASIC > Java Bin Path`
- Open folders at the **account level** for best results (not individual files)
- Use `$INCLUDE` for shared code — the extension resolves includes for go-to-definition
- The extension provides IntelliSense for BASIC statements, cataloged programs (CALL), and symbols in the workspace
