### VS Code Settings, create a git repository for your settings:

#### Windows location
`%APPDATA%\Code\User`

#### Linux location
`$HOME/.config/Code/User`

### Extension 
dump extensions:
    code --list-extensions > extensions.txt

### Use vim, trust me:
https://openvim.com/

## VS Code Learning Hour

If you only have one hour, learn the features in this order.

### 0 to 10 min: Command Palette
The Command Palette is the fastest way to discover VS Code.

- Open it with `Ctrl+Shift+P`
- Search for commands by name instead of hunting through menus
- Good starter commands:
    - `Preferences: Open User Settings (JSON)`
    - `Tasks: Run Task`
    - `View: Toggle Terminal`
    - `Git: Clone`
    - `Extensions: Install Extensions`

Rule of thumb:
If you do not know where a feature lives, start in the Command Palette.

### 10 to 20 min: Editor basics
Get comfortable moving around files quickly.

- `Ctrl+P`: quick open files by name
- `Ctrl+Shift+O`: jump to symbol in current file
- `F12`: go to definition
- `Alt+Left` and `Alt+Right`: go back and forward
- Multi-cursor: `Alt+Click` or `Ctrl+Alt+Up/Down`
- Rename symbol: `F2`
- Format document: usually `Shift+Alt+F`

Focus on these habits:
- Open files with search instead of drilling through folders
- Jump to definitions instead of scrolling
- Rename through the editor instead of manual search-and-replace when language support exists

### 20 to 30 min: Search and refactor
VS Code is much faster once you use workspace search well.

- `Ctrl+Shift+F`: search across the workspace
- `Ctrl+H`: replace in current file
- Use include and exclude globs in the search panel
- Use symbol rename when possible, plain text replace only when necessary

Best use cases:
- Find config keys across the repo
- Trace a feature by searching command IDs, setting names, or function names
- Update repeated text carefully with preview before replace

### 30 to 40 min: Terminal, tasks, and automation
Use the integrated terminal for project commands and tasks for repeatable workflows.

- Open terminal with `` Ctrl+` ``
- Use `tasks.json` for repeatable commands like build, test, export, codegen, or setup
- Keep one-off experiments in the terminal, not in tasks
- Use `preLaunchTask` when debug should build first

Good task examples:
- build C++ with CMake
- run Python tests
- export installed extensions
- run linters or formatters

### 40 to 50 min: Debugging
Use `launch.json` when you need debugger features.

- Set a breakpoint by clicking left of the line number
- Start debugging with `F5`
- Step over with `F10`
- Step into with `F11`
- Inspect variables, watch expressions, and call stack in the Run and Debug view

Use a task when you just want to run a command.
Use a launch config when you need breakpoints, step-through execution, or attach mode.

### 50 to 60 min: Git, extensions, and customization
These are the force multipliers.

- Source Control view shows changed files, diffs, staging, and commits
- Extensions view lets you add language servers, themes, formatters, debuggers, and tooling
- Settings Sync can carry settings, extensions, and keybindings across machines
- Profiles let you keep different setups for different kinds of work

Recommended habits:
- Keep user settings in git if you want reproducible setup
- Prefer a small set of high-value extensions over many overlapping ones
- Use snippets for repeated headers, templates, or boilerplate

## Fast mental model

- `settings.json`: editor and tool behavior
- `keybindings.json`: shortcuts
- `snippets/`: reusable text expansions
- `tasks.json`: repeatable commands
- `launch.json`: debugging and run-under-debugger
- `.code-workspace`: multi-root workspace definition

## First-hour checklist

- Learn `Ctrl+Shift+P`
- Learn `Ctrl+P`
- Learn `Ctrl+Shift+F`
- Learn `F12` and `F2`
- Learn terminal plus one useful task
- Learn one debugger launch config
- Learn where user settings live

### Tasks vs Launch
Use `tasks.json` when you want VS Code to run a command such as build, test, format, backup extensions, or start a tool/script without attaching a debugger.

Use `launch.json` when you want VS Code to run or attach with debugging features such as breakpoints, call stack, variables, watch, and step-through execution.

Typical split:
- `tasks.json`: build with CMake, run linters, export extensions, generate files, start helper tools
- `launch.json`: debug Python, debug C++, attach to a running process, launch an app under the debugger

Common pattern:
- Put repeatable shell commands in `tasks.json`
- Put debug/run configurations in `launch.json`
- If needed, call a task from a launch config using `preLaunchTask`

### Workspace
Workspace multi folder project structure:

```
my-workspace/
│
├── python-app/
│   ├── main.py
│   └── .vscode/
│       └── settings.json
│
├── cpp-app/
│   ├── main.cpp
│   └── .vscode/
│       ├── tasks.json
│       └── launch.json
│
└── my.code-workspace
```
