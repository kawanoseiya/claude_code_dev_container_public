👉 日本語版はこちら: [README.ja.md](./README.ja.md)

# 🚀 Claude Code Dev Container

This repository provides a ready-to-use template for setting up the [Claude Code CLI](https://docs.anthropic.com/claude/docs/claude-code) in a **VS Code Dev Container** environment.

> 🧑‍💻 **What is a Dev Container?**  
> A Dev Container is a feature of Visual Studio Code (VS Code) that allows you to automatically set up a complete development environment inside a container, with all tools and configurations pre-installed.  
> It simplifies the setup process and makes development more portable and reproducible.

---

## ⚙️ Setup Instructions

### 1️⃣ Prerequisites

Please install the following tools before starting:

| Tool | Purpose | Download Link |
|------|---------|---------------|
| [Visual Studio Code](https://code.visualstudio.com/) | Main editor supporting Dev Containers | ✅ Required |
| [Dev Containers Extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) | VS Code extension for containerized environments | ✅ Required |
| [Docker Desktop](https://www.docker.com/products/docker-desktop/) | Required runtime for local containers | ✅ Required (for local use) |

> 💡 If you're using **GitHub Codespaces**, you do not need to install Docker Desktop locally.

---

### 2️⃣ Launching the Dev Container

1. Open this repository in VS Code.
2. Open the command palette (`Cmd+Shift+P` or `Ctrl+Shift+P`) and select `Reopen in Container`.
3. The Dev Container will automatically install Claude Code CLI, and the `claude` command will become available.

---

### 3️⃣ Setting the API Key

The first time you run the `claude` command, you’ll be prompted to enter your API key.  
Follow the instructions in the terminal to complete the setup.

---

## 🖥️ Basic Usage

Open a terminal in VS Code and run:

```bash
claude
```

During the initial setup, you can run the following commands (in order):

| Command | Description |
|---------|-------------|
| `/init` | Creates `CLAUDE.md` and defines your project specifications |
| `/terminal-setup` | Sets up terminal integration and enhancements |
| `/install-github-app` | (Optional) Sets up GitHub Actions integration |
| `/migrate-installer` | (Optional) Migrates from global to local install |

> ⌨️ **Helpful Shortcuts**  
> - `Cmd+Esc` (Mac) or `Ctrl+Esc` (Windows) to launch Claude Code  
> - `Ctrl+Alt+K` to insert `@File` references

---

## 🛠 Example: Create a Simple Script Using Claude

1. Launch `claude`
2. Run `/init` to generate `CLAUDE.md`
3. Ask Claude:
   ```
   create a bash script that backs up my project folder
   ```
4. Review and save the suggested script
5. Run the script and verify its behavior

---

## 💡 Example: Building an App with Claude

1. Start `claude`
2. Run `/init` and write your app specifications in `CLAUDE.md`
3. Ask Claude:
   ```
   Based on the above specs, design and implement a Flutter project
   ```
4. Review Claude’s suggestions and ask for improvements if needed
5. Divide implementation into modules and generate test code as well

---

## 📁 Directory Structure

| File / Directory | Description |
|------------------|-------------|
| `.devcontainer/devcontainer.json` | Dev Container settings with Claude CLI configured |
| `.devcontainer/README.md` | Documentation for the container setup |

---

## ⚠️ Notes

- The `claude` command is automatically available after the Dev Container starts.
- **Do not use npx or npm**. Always run `claude` inside the Dev Container.
- Always **review Claude's output** and verify its safety and correctness before use.
- If using the Claude Code VS Code extension, you can launch it with `Cmd+Esc`.

---

## 🧪 Troubleshooting

### Dev Container won't start?

- Ensure Docker Desktop is running
- Check that the Dev Containers extension is installed and enabled
- Try restarting VS Code and run `Reopen in Container` again

---

## 📚 Resources

- [Dev Container Features Spec](https://containers.dev/implementors/features/)
- [Claude Code Documentation](https://docs.anthropic.com/claude/docs/claude-code)
- [Claude Code Security Guide](https://docs.anthropic.com/claude/docs/claude-code-security)
- [Claude Code IDE Integrations](https://docs.anthropic.com/claude/docs/claude-code-ide-integrations)

---

> 💬 Feedback and contributions are welcome via Issues or Pull Requests.
