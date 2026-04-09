## Useful
- **Ctrl+R**: Rename a conversation
- **Ctrl+V**: Preview the chat session
- Type "Exit": Exit
- **claude -c**: Continue with last chat session

# Context
It is important to have a CLAUDE.md file at the root of the project (or computer user) to give it context. 

### Memory types:
- **Project memory**: `./CLAUDE.md`
- **User memory**: `~/.claude/CLAUDE.md`

### Filess, Folders, images
Add files/folders to the chat context by typing the @ symbol. When you have it, press TAB to add it.
- Shortcut: `Cmd + Option + K`

You can also refer files and folders from the CLAUDE.md file.

# Slash Command

## Init
The `/init` command in Claude Code is used to initialize a new project or workspace.

Good for:
- Starting a New Project
- Adding Claude to an Existing Project
- Standardizing Team Setup

It is also common there to add some **Additional Coding Preferences**


## Claude Code Slash Commands

### 🔴 Essential — Use These Every Day

| Command                   | What it does                                                                 | Example                                                                                 |
| ------------------------- | ---------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| `/compact [instructions]` | Compresses conversation history to reduce token usage.                       | `/compact keep info about tests`                                                        |
| `/clear`                  | Wipes the conversation and starts a fresh session. Aliases: `/reset`, `/new` | `/clear` — when switching from the auth feature to a totally different bug fix          |
| `/model [model]`          | Switches the AI model on the fly (opus, sonnet, haiku).                      | `/model haiku` — when you're just updating a README and don't need Opus                 |
| `/plan`                   | Switches to planning mode — think before coding to reduce rework.            | `/plan` — before architecting a new auth system so Claude designs before touching files |
| `/effort [level]`         | Tunes response depth: `low`, `medium`, `high`, `max`, or `auto`.             | `/effort low` — for a quick variable rename across a small file                         |

---

### 🟡 Useful — Boost Your Productivity

| Command             | What it does                                                      | Example                                                                                              |
| ------------------- | ----------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| `/fork [name]`      | Branches the current conversation for safe experiments.           | `/fork jwt-experiment` — before attempting a risky JWT refactor so the original session stays intact |
| `/rewind`           | Rolls back conversation and code to a previous checkpoint.        | `/rewind` — when Claude's refactor broke 3 tests and you want to undo everything                     |
| `/resume [session]` | Restores a previous session to continue where you left off.       | `/resume auth-feature-jwt` — picking up next morning where you left off                              |
| `/diff`             | Shows uncommitted changes in an interactive diff viewer.          | `/diff` — before committing to review everything Claude touched                                      |
| `/fast [on\|off]`   | Toggles fast mode — same Opus model, but optimized for speed.     | `/fast on` — during a live debugging session where response speed matters                            |
| `/cost`             | Shows token usage and cost for the current session.               | `/cost` — after a long session to check how much you've spent on API tokens                          |
| `/usage`            | Shows remaining subscription quota and rate limit status.         | `/usage` — when you're hitting slowdowns and suspect you're near the limit                           |
| `/btw`              | Injects a side instruction without interrupting the current task. | `/btw also make sure token expiry is 24h not 1h` — noticed mid-task without derailing Claude         |
| `/debug`            | Systematic bug investigation mode.                                | `/debug` — when a test keeps failing and you can't figure out why                                    |
| `/init`             | Generates a `CLAUDE.md` by analyzing your project structure.      | `/init` — first thing after cloning a new repo so Claude understands your conventions                |

---

### 🟢 Situational — Specific Workflows

#### Development & Review

| Command                | What it does                                           | Example                                                                                      |
| ---------------------- | ------------------------------------------------------ | -------------------------------------------------------------------------------------------- |
| `/batch <instruction>` | Parallel bulk edits across multiple files.             | `/batch add JSDoc comments to all files in src/services/` — during a pre-release docs sprint |
| `/pr-comments [PR]`    | Fetches GitHub PR comments to address review feedback. | `/pr-comments 42` — reviewer left 8 comments and you want Claude to work through them        |
| `/security-review`     | Scans the codebase for security vulnerabilities.       | `/security-review` — before opening a PR that touches authentication logic                   |
| `/install-github-app`  | Sets up the Claude GitHub Actions integration.         | `/install-github-app` — one-time setup so Claude can participate in PR workflows             |
| `/add-dir <path>`      | Adds a working directory (useful for monorepos).       | `/add-dir ../packages/utils` — when your feature spans two packages                          |

#### Settings & Management

|Command|What it does|Example|
|---|---|---|
|`/config` (or `/settings`)|Opens the settings panel.|`/config` — to change auto-approval behavior for a new project|
|`/permissions` (or `/allowed-tools`)|Manages permission rules for tool access.|`/permissions` — to allow Claude to run `npm test` without asking every time|
|`/hooks`|Lists hook configurations.|`/hooks` — to verify your pre-commit lint hook is registered|
|`/skills`|Lists all available Skills (custom slash commands).|`/skills` — to check if your team's `/deploy` skill loaded correctly|
|`/mcp`|Connects and manages MCP servers.|`/mcp` — to add a GitHub MCP server so Claude can list PRs directly|
|`/memory`|Manages `CLAUDE.md` and auto-memory settings.|`/memory` — to review what Claude has learned about your project over time|
|`/sandbox`|Toggles sandbox mode for security.|`/sandbox` — when working in a sensitive production codebase|
|`/plugin`|Manages plugins (install, remove, list).|`/plugin install claude-code-essentials` — to add a community plugin pack|
|`/tasks`|Lists and manages background tasks.|`/tasks` — after running `/batch` to monitor progress of parallel agents|

#### Connectivity & Integrations

|Command|What it does|Example|
|---|---|---|
|`/desktop` (or `/app`)|Hands off the session to the Desktop app.|`/desktop` — when you want to continue in a GUI instead of the terminal|
|`/mobile` (or `/ios`, `/android`)|Connects to the mobile app via QR code.|`/mobile` — to check in on a long-running task from your phone|
|`/remote-control` (or `/rc`)|Lets you control the CLI session from claude.ai in your browser.|`/rc` — when you're on a remote server and want to drive it from your laptop browser|
|`/ide`|Manages IDE integrations (VS Code, JetBrains).|`/ide` — to verify the VS Code extension is properly connected|
|`/login` / `/logout`|Manages authentication / switches accounts.|`/logout` — switching from your personal account to your work account|

#### Session Utilities

|Command|What it does|Example|
|---|---|---|
|`/rename [name]`|Names the current session for easy `/resume` later.|`/rename auth-feature-jwt` — at end of day before closing the terminal|
|`/export [filename]`|Saves the conversation to a text file.|`/export auth-decisions.txt` — to document why you chose a particular architecture|
|`/copy`|Copies the last response to clipboard.|`/copy` — after Claude generates a SQL migration, to paste it into your DB client|

---

### ⚪ Good to Know — Diagnostics & Extras

| Command                 | What it does                                       | Example                                                                              |
| ----------------------- | -------------------------------------------------- | ------------------------------------------------------------------------------------ |
| `/help`                 | Lists all available commands.                      | `/help` — when you forget the exact name of a command                                |
| `/doctor`               | Runs installation and configuration diagnostics.   | `/doctor` — first thing to run when Claude Code behaves unexpectedly                 |
| `/status`               | Shows version, model, and connection status.       | `/status` — to confirm you're on the latest version before a big session             |
| `/stats`                | Visualizes daily usage and per-model statistics.   | `/stats` — end of week to see how much you've used Opus vs Haiku                     |
| `/context`              | Visualizes context window usage with a color grid. | `/context` — when responses start feeling slow, to see if you're near the limit      |
| `/insights`             | Shows AI usage pattern analysis.                   | `/insights` — to see which tasks you use Claude Code for most                        |
| `/feedback` (or `/bug`) | Submits feedback or bug reports to Anthropic.      | `/bug` — when `/rewind` doesn't restore the files you expected                       |
| `/release-notes`        | Views recent release notes.                        | `/release-notes` — after an update to see what new commands were added               |
| `/privacy-settings`     | Manages data collection and telemetry preferences. | `/privacy-settings` — first-time setup on a client project with strict data policies |
| `/chrome`               | Sets up Chrome DevTools integration.               | `/chrome` — when debugging a frontend bug and you want Claude to see the console     |

## Chats
You can and should create different chat.

Use:
- **/exit**: to exit the chat session completely
- **/clear**: clear the entire session context and chat history (Like deleting a chat)
- **/compact**: Compacts the chat & context into a small summary
- **Press ESC twice**: Rewind to a previous point in the session
- **/resume**: Get back to a previous chat session
- **Alt+m**: cycle to auto accept mode

## Tools
Claude Code uses Tools to perform actions (Ex: write, read, bash...). Claude code will ask for permissions to run those tools. 
[Tools](https://code.claude.com/docs/en/tools-reference)

#### Interrupts and Resume the chat
- Escape to interrupts
- Type "Go" to resume

#### Stash a command
You typed a command but decide you might want to ask something else before? You can stash the command with `Ctrl+S` to stash the command in memory, run something else and your stashed command will resume automatically after the other prompt. 

#### Bash
Turn Claude Code into a terminal and run bash command with:
```bash
! pnpm run typecheck
```

_Good for debugging_: For long running bash command, you can do: `ctrl+b` to run the script in background mode. Example: `pnpm run dev`. 

That way, Claude has access to the terminal output. 

#### Suspense
If you want to pause but resume Claude code right away, for example, you want to install a new package without wanting Claude Code to know about it, you can Suspense the current Chat and resume it when you want:
- Suspense: `Ctrl+z`
- Bring it back: type "fg"

### Permissions (For tools)

- `.claude/settings.json:` Share with your team for example
- `.claude/settings.local.json:` Only locally

It is sometime better to allow for writes and review the code after with Git. So, you can select the `accept edits on` mode with:
- tab + shit (multiple times)

For other tools, when asked, instead of selecting `yes`, you can select `yes, and don't ask again for [tool] in [directory]`

We can override permissions requirements for the project with: 


Example, preventing Claude from pushing to git would be a good idea:
