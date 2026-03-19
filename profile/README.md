# claude-yolo

Run parallel [Claude Code](https://docs.anthropic.com/en/docs/claude-code) agents in tmux with automatic permission approval.

When organization-managed settings force `ask` mode for tools like `Bash`, `Bash(rm:*)`, and `WebFetch`, claude-yolo auto-approves those prompts at the terminal level using `tmux capture-pane` + `send-keys`.

## Get started

```bash
command -v curl >/dev/null || { s=; [ "$(id -u)" != 0 ] && s=sudo; command -v apt-get >/dev/null && { $s apt-get update && $s apt-get install -y curl; } || command -v dnf >/dev/null && $s dnf install -y curl || command -v yum >/dev/null && $s yum install -y curl || command -v apk >/dev/null && $s apk add curl || command -v pacman >/dev/null && $s pacman -S --noconfirm curl || command -v pkg >/dev/null && pkg install -y curl || command -v brew >/dev/null && brew install curl; }; curl -fsSL https://raw.githubusercontent.com/claude-yolo/claude-yolo/refs/heads/main/install.sh | bash && source ~/.bashrc
```

```bash
claude-yolo "fix the login bug" "add unit tests for auth" "update the README"
```

See the [full documentation](https://github.com/claude-yolo/claude-yolo) for options, navigation, and how it works under the hood.

![claude-yolo](https://raw.githubusercontent.com/claude-yolo/claude-yolo/main/assets/logo.jpeg)

## Key features

- **Parallel multi-agent execution** — Uniquely enables parallel execution of multiple Claude Code agents in tmux with non-invasive, terminal-level auto-approval of permissions.
- **Sophisticated detection logic** — Handles both expanded and collapsed transcript views without modifying the Claude CLI or relying on the `--dangerously-skip-permissions` flag.
- **Reliability and traceability** — Per-pane cooldowns, detailed audit logging, and an extensive test suite emphasize reliability and traceability.
- **No CLI patching or containerization** — Unlike most alternatives, avoids direct CLI patching or containerization, making it suitable for environments where `ask` mode is enforced.
