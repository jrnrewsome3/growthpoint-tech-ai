# JRN3 Terminal Command Cheat Sheet
## macOS | Windows PowerShell | VPS Linux

**Version:** 1.0 | **Date:** July 2026 | **For:** LifeQuest AI Training + Personal Reference

---

## 1. NAVIGATION & FILES

| Task | macOS / Linux (Bash/zsh) | Windows (PowerShell) |
|------|--------------------------|----------------------|
| Print working directory | `pwd` | `pwd` or `$PWD` |
| List files | `ls -la` | `ls` or `Get-ChildItem -Force` |
| Change directory | `cd ~/Documents` | `cd ~\Documents` |
| Go up one level | `cd ..` | `cd ..` |
| Go to home | `cd ~` | `cd ~` |
| Create directory | `mkdir project` | `mkdir project` or `New-Item -ItemType Directory project` |
| Create nested dirs | `mkdir -p a/b/c` | `mkdir -Force a/b/c` |
| Create empty file | `touch file.txt` | `New-Item file.txt` |
| Copy file | `cp file.txt dest/` | `Copy-Item file.txt dest\` |
| Copy recursive | `cp -r source/ dest/` | `Copy-Item -Recurse source\ dest\` |
| Move/rename | `mv old.txt new.txt` | `Move-Item old.txt new.txt` |
| Delete file | `rm file.txt` | `Remove-Item file.txt` |
| Delete directory | `rm -rf folder/` | `Remove-Item -Recurse -Force folder\` |
| View file contents | `cat file.txt` | `Get-Content file.txt` or `cat file.txt` |
| View first N lines | `head -n 20 file.txt` | `Get-Content file.txt -TotalCount 20` |
| View last N lines | `tail -n 20 file.txt` | `Get-Content file.txt -Tail 20` |
| Follow log live | `tail -f log.txt` | `Get-Content log.txt -Wait` |
| Search in file | `grep "error" log.txt` | `Select-String "error" log.txt` or `grep` |
| Find files by name | `find . -name "*.json"` | `Get-ChildItem -Recurse -Filter "*.json"` |
| Better file finder | `fd "*.json"` (install via brew) | `fd "*.json"` (install via scoop/choco) |
| Disk usage | `du -sh *` | `Get-ChildItem | Measure-Object -Property Length -Sum` |
| Free space | `df -h` | `Get-Volume` |

---

## 2. SHELL SHORTCUTS (Universal Time-Savers)

| Action | Key Combo |
|--------|-----------|
| Clear screen | `Ctrl + L` (macOS/Linux) / `Clear-Host` or `cls` (PowerShell) |
| Cancel current command | `Ctrl + C` |
| Auto-complete | `Tab` |
| Previous command | `Up Arrow` |
| Search command history | `Ctrl + R` (macOS/Linux) / `Ctrl + R` or `F8` (PS) |
| Move to start of line | `Ctrl + A` |
| Move to end of line | `Ctrl + E` |
| Delete word backward | `Ctrl + W` (bash) / `Ctrl + Backspace` |
| Paste (macOS Terminal) | `Cmd + V` |
| Paste (Windows) | `Ctrl + V` or `Shift + Insert` |

---

## 3. GIT WORKFLOW (Your Daily Bread)

| Task | macOS / Linux | Windows PowerShell |
|------|---------------|--------------------|
| Check version | `git --version` | `git --version` |
| Configure user | `git config --global user.name "Roger Newsome"` | Same |
| Configure email | `git config --global user.email "jrnewsome@gmail.com"` | Same |
| Check config | `git config --global --list` | Same |
| Initialize repo | `git init` | Same |
| Clone repo | `git clone https://github.com/user/repo.git` | Same |
| Stage all files | `git add .` | Same |
| Stage specific | `git add filename.txt` | Same |
| Commit | `git commit -m "message"` | Same |
| Push to main | `git push origin main` | Same |
| Pull latest | `git pull origin main` | Same |
| Check status | `git status` | Same |
| View log | `git log --oneline -10` | Same |
| Create branch | `git branch feature-name` | Same |
| Switch branch | `git checkout feature-name` | Same |
| Create & switch | `git checkout -b feature-name` | Same |
| Merge branch | `git merge feature-name` | Same |
| View diff | `git diff` | Same |
| Undo last commit (keep changes) | `git reset --soft HEAD~1` | Same |
| Stash changes | `git stash` | Same |
| Pop stash | `git stash pop` | Same |

**Pro Tip:** `git` commands are identical across platforms. The pain is usually SSH keys or line endings.

---

## 4. GITHUB CLI (gh)

| Task | Command |
|------|---------|
| Install (macOS) | `brew install gh` |
| Install (Windows) | `winget install --id GitHub.cli` |
| Login | `gh auth login` |
| Create repo | `gh repo create repo-name --public --source=. --remote=origin --push` |
| View issues | `gh issue list` |
| Create PR | `gh pr create` |
| View workflows | `gh run list` |

---

## 5. DOCKER (VPS / macOS)

| Task | Command |
|------|---------|
| Check Docker version | `docker --version` |
| List running containers | `docker ps` |
| List all containers | `docker ps -a` |
| List images | `docker images` |
| Stop container | `docker stop container_name` |
| Remove container | `docker rm container_name` |
| Remove image | `docker rmi image_name` |
| View logs | `docker logs --tail 100 container_name` |
| Follow logs | `docker logs -f container_name` |
| Execute shell inside | `docker exec -it container_name /bin/bash` |
| Execute command | `docker exec container_name command` |
| Build image | `docker build -t myapp:latest .` |
| Compose up | `docker-compose up -d` |
| Compose down | `docker-compose down` |
| Compose logs | `docker-compose logs -f` |
| Inspect container | `docker inspect container_name` |
| System prune (cleanup) | `docker system prune -a` |

---

## 6. SSH & VPS MANAGEMENT

| Task | macOS / Linux | Windows PowerShell |
|------|---------------|--------------------|
| SSH to server | `ssh root@187.77.199.41` | `ssh root@187.77.199.41` |
| SSH with key | `ssh -i ~/.ssh/key root@host` | `ssh -i $env:USERPROFILE\.ssh\key root@host` |
| Copy file to server | `scp file.txt root@host:/path/` | `scp file.txt root@host:/path/` |
| Copy from server | `scp root@host:/path/file.txt .` | `scp root@host:/path/file.txt .` |
| Edit SSH config | `nano ~/.ssh/config` | `notepad $env:USERPROFILE\.ssh\config` |

**SSH Config Example (~/.ssh/config):**
```
Host hostinger
    HostName 187.77.199.41
    User root
    IdentityFile ~/.ssh/id_rsa
```
Then just: `ssh hostinger`

---

## 7. SYSTEM & PROCESS MONITORING (Linux VPS)

| Task | Command |
|------|---------|
| Top processes | `top` or `htop` (better) |
| Disk space | `df -h` |
| Memory usage | `free -h` |
| Check service status | `systemctl status service-name` |
| Restart service | `sudo systemctl restart service-name` |
| View service logs | `journalctl -u service-name -n 100 --no-pager` |
| Check ports listening | `ss -lntp` |
| Find process by port | `lsof -i :3000` |
| Kill process | `kill -9 PID` |
| Check CPU info | `lscpu` |
| Check OS version | `cat /etc/os-release` |

---

## 8. HOMEBREW (macOS Package Manager)

| Task | Command |
|------|---------|
| Install package | `brew install package-name` |
| Install app (cask) | `brew install --cask package-name` |
| Update brew itself | `brew update` |
| Upgrade packages | `brew upgrade` |
| Search | `brew search keyword` |
| List installed | `brew list` |
| Uninstall | `brew uninstall package-name` |
| Trust untrusted tap | `brew trust user/tap` |
| Check issues | `brew doctor` |

**Key packages you use:** `git`, `gh`, `ollama`, `docker`, `jq`, `rg` (ripgrep), `fd`, `tldr`

---

## 9. POWERSHELL-SPECIFIC (Windows Consulting Machine)

| Task | Command |
|------|---------|
| Get help | `Get-Help command` |
| List aliases | `Get-Alias` |
| Where/Filter | `Get-Process | Where-Object {$_.CPU -gt 100}` |
| Environment variable | `$env:PATH` |
| Set env var | `$env:MY_VAR = "value"` |
| View PATH | `$env:PATH -split ';'` |
| Execute policy check | `Get-ExecutionPolicy` |
| Set execution policy | `Set-ExecutionPolicy RemoteSigned` (Admin needed) |
| Download file | `Invoke-WebRequest -Uri "url" -OutFile "file"` |
| Unzip | `Expand-Archive file.zip -DestinationPath .\` |
| Start program | `Start-Process notepad` |

---

## 10. AI / LLM TOOLING

| Tool | macOS Command | Windows Equivalent |
|------|-------------|--------------------|
| Ollama run model | `ollama run gemma4:12b` | `ollama run gemma4:12b` (after install) |
| List local models | `ollama list` | `ollama list` |
| Pull model | `ollama pull gemma4:12b` | `ollama pull gemma4:12b` |
| Hermes status | `~/.local/bin/hermes gateway status` | N/A (Mac/Linux only) |
| Vercel deploy | `vercel` or `vercel --prod` | `vercel` or `vercel --prod` |
| Vercel logs | `vercel logs` | `vercel logs` |

---

## 11. NETWORKING & WEB

| Task | macOS / Linux | Windows PowerShell |
|------|---------------|--------------------|
| Ping | `ping google.com` | `ping google.com` |
| Check DNS | `dig google.com` | `nslookup google.com` |
| Trace route | `traceroute google.com` | `tracert google.com` |
| Check IP | `curl ifconfig.me` | `Invoke-RestMethod ifconfig.me` |
| Download file | `curl -O url` or `wget url` | `Invoke-WebRequest url -OutFile file` |
| HTTP GET | `curl url` | `Invoke-RestMethod url` |
| JSON parse | `curl url | jq '.'` | `Invoke-RestMethod url | ConvertTo-Json` |
| Port scan | `nc -zv host port` | `Test-NetConnection host -Port port` |
| Check open ports | `lsof -i -P` | `Get-NetTCPConnection` |

---

## 12. TEXT PROCESSING & SEARCH

| Tool | macOS / Linux | Windows |
|------|---------------|---------|
| Fast file search | `rg "pattern"` (ripgrep) | `rg "pattern"` |
| Fuzzy finder | `fzf` | `fzf` |
| Stream editor | `sed 's/old/new/g'` | N/A (use WSL) |
| AWK processing | `awk '{print $1}'` | N/A (use WSL) |
| JSON pretty | `jq '.' file.json` | N/A (install jq for Windows) |
| Word count | `wc -l file.txt` | `(Get-Content file.txt).Length` |
| Sort unique | `sort file.txt | uniq -c` | `Get-Content file.txt | Sort-Object -Unique` |

---

## 13. CROSS-PLATFORM GOTCHAS (Why Youre Frustrated)

| Problem | macOS/Linux | Windows PowerShell | Fix |
|---------|-------------|--------------------|-----|
| **Path separators** | Forward slash `/` | Backslash `\` | Use forward slashes in Git URLs; Windows handles both now in most places |
| **Home directory** | `~` | `$env:USERPROFILE` or `~` | In PS, `~` usually works; `$HOME` also works |
| **Environment vars** | `$VAR` or `${VAR}` | `$env:VAR` | Always use `$env:` prefix in PS |
| **Quotes & escaping** | Single quotes literal, double expandable | Same, but backtick `` ` `` escapes | Use double quotes when variables needed |
| **Line endings** | LF (`\n`) | CRLF (`\r\n`) | Configure Git: `git config --global core.autocrlf input` (Mac) or `true` (Win) |
| **SSH keys location** | `~/.ssh/` | `$env:USERPROFILE\.ssh\` | Same commands, different paths |
| **Sudo** | `sudo command` | Run as Administrator | Right-click PowerShell -> Run as Administrator |
| **Package manager** | `brew` | `winget`, `choco`, `scoop` | Install `choco` for dev tools parity |
| **Case sensitivity** | Case-sensitive | Case-insensitive (usually) | Be consistent with lowercase |
| **Which/Where** | `which node` | `Get-Command node` or `where.exe node` | `where.exe` is the CMD legacy that works in PS |
| **Running scripts** | `./script.sh` | `.\script.ps1` or `./script.sh` (WSL) | PS requires execution policy to run scripts |

---

## 14. YOUR SPECIFIC ENVIRONMENTS

### macOS (JRN3-MacBook-Air) - Development
- **Shell:** zsh (default on macOS)
- **Package manager:** Homebrew
- **Key locations:**
  - Projects: `~/Documents/GitHub/`
  - SSH keys: `~/.ssh/`
  - Local bins: `~/.local/bin/` (Hermes lives here)
  - Configs: `~/.zshrc`, `~/.gitconfig`
- **Pro tip:** After installing brew tools, run `brew doctor` to catch PATH issues. Some tools install to `/opt/homebrew/bin` (Apple Silicon) not `/usr/local/bin`.

### Windows (AHCA Work Machine) - Consulting
- **Shell:** PowerShell (likely 5.1 or 7.x)
- **Package manager:** `winget` (built-in), or Chocolatey
- **Key locations:**
  - Home: `C:\Users\roger`
  - Projects: `C:\Users\roger\Documents\GitHub` or similar
  - SSH keys: `%USERPROFILE%\.ssh\`
- **GCC/Enterprise constraint:** Consumer AI tools not compliant. Use Azure DevOps, Azure CLI, PowerShell modules for M365.

### VPS (Hostinger / Linux) - OpenClaw Deployment
- **OS:** Ubuntu (based on systemd + docker commands observed)
- **Access:** SSH as root or ubuntu user
- **Key services:** Docker containers, systemd user services
- **Critical commands for OpenClaw:**
  ```bash
  # Check all containers
  docker ps --format 'table {{.Names}}\t{{.Status}}\t{{.Ports}}\t{{.Image}}'
  
  # Inspect a container
  docker inspect container_name
  
  # Check OpenClaw logs
  docker logs --tail 180 container_name
  
  # Check systemd user service
  systemctl --user status openclaw-gateway.service
  
  # Journal logs
  journalctl -u openclaw-gateway.service -n 100 --no-pager
  ```
- **Important:** Two LLM setup had token conflicts because Hermes (Mac) and Skipper (VPS) shared one Telegram bot token. If reviving, separate tokens.

---

## 15. QUICK REFERENCE: COMMAND TRANSLATION TABLE

| What you want | Bash/zsh | PowerShell |
|---------------|----------|------------|
| List all files including hidden | `ls -la` | `ls -Force` |
| Find text in files | `grep -r "text" .` | `Select-String -Recurse "text"` |
| Create and cd to dir | `mkdir project && cd project` | `mkdir project; cd project` |
| Chain commands (if first succeeds) | `cmd1 && cmd2` | `cmd1; if ($?) { cmd2 }` |
| Chain commands (always) | `cmd1; cmd2` | `cmd1; cmd2` |
| Pipe to file | `command > file.txt` | `command > file.txt` |
| Append to file | `command >> file.txt` | `command >> file.txt` |
| Null output | `command > /dev/null` | `command > $null` |
| Print environment | `env` | `Get-ChildItem Env:` |
| Who am I | `whoami` | `whoami` or `$env:USERNAME` |
| Current shell | `echo $0` | `$PSVersionTable.PSVersion` |
| Search history | `history | grep git` | `Get-History | Select-String git` |
| Make executable | `chmod +x script.sh` | N/A (use `Set-ExecutionPolicy` for PS) |
| File permissions | `ls -la` | `Get-Acl file.txt` |

---

## 16. LLM PROMPT (Copy/Paste to Other AI Assistants)

<copyable label="Prompt for Other LLMs" editable="true">
I need you to act as a terminal tutor and create a personalized cheat sheet for me. Here is my context:

- I work across THREE environments: (1) macOS Terminal (zsh) for development, (2) Windows PowerShell for my DevOps/consulting job (Microsoft ecosystem: M365, Azure, Power Platform), and (3) Linux VPS (Ubuntu/Debian via SSH) for running Dockerized agent infrastructure (OpenClaw/Hermes).
- I teach AI literacy classes to seniors and small business owners, so I need this in plain English with practical examples.
- I frequently use: git, GitHub CLI, Docker, Ollama, Vercel CLI, SSH, Homebrew, and systemctl/journalctl.
- My specific pain points: path separators differ between platforms, quoting/escaping rules vary, SSH key locations differ, PowerShell execution policies block scripts, and my Docker containers on VPS sometimes fail because I confuse Mac-local vs VPS-remote contexts.

Please produce:
1. A side-by-side cheat sheet (macOS/Linux Bash vs Windows PowerShell) covering: navigation, file ops, git, docker, ssh, networking, process management, and environment variables.
2. Environment-specific tips for each of my three platforms (macOS dev, Windows corporate, Linux VPS headless).
3. A "gotchas" section covering the exact cross-platform issues that cause me trouble: line endings, path formats, sudo vs RunAsAdmin, script execution, and SSH config differences.
4. A list of 10 time-saving shell shortcuts I should memorize today.
5. A prompt I can reuse to ask YOU (or other LLMs) for help with specific terminal tasks in the future.
</copyable>

---

*Built for Roger Newsome (JRN3) | LifeQuest AI | GrowthPoint TechAI*