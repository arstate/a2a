# AIStudio2API — AI Agent Bootstrap (`arstate/a2a`)

> **Quick Prompt for Humans (Linux / macOS / Windows):**
> Kirim link repo ini ke AI Agent lu (OpenCode, Claude Code, Antigravity, Cursor, Windsurf, Codex) lalu ketik:
> *"Baca `https://github.com/arstate/a2a`, download & unzip paketnya, lalu baca detail README di dalam folder hasil ekstrak untuk setup AIStudio2API di mesin gw sampai port 2048 nyala."*

---

## Mandatory Instructions for AI Agent

This repository intentionally contains **only this bootstrap `README.md`**.
The complete multi-OS package (installers, Linux binary archive, full source clones, and detailed OS-specific guides) is hosted in the permanent release archive below.

**Do NOT guess setup steps from memory.** Follow Steps 1 -> 3 in order:

### Step 1: Download the Package ZIP

- **Permanent Public ZIP URL:** `https://github.com/arstate/a2a/releases/download/v1/AIStudio2API.zip`
- **Size:** 93,893,461 bytes (~89.5 MB)
- **SHA-256:** `9b6856b419b42bb93b628bd6381bef5970fbf2d305fb983d6564e749d6e75aee`

#### Linux / macOS
```bash
mkdir -p ~/a2a-pkg && cd ~/a2a-pkg
curl -fSL -o AIStudio2API.zip "https://github.com/arstate/a2a/releases/download/v1/AIStudio2API.zip"
```

#### Windows (PowerShell)
```powershell
$ProgressPreference = 'SilentlyContinue'
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
$PkgDir = Join-Path $env:USERPROFILE "a2a-pkg"
New-Item -ItemType Directory -Force -Path $PkgDir | Out-Null
$ZipFile = Join-Path $PkgDir "AIStudio2API.zip"
Invoke-WebRequest -Uri "https://github.com/arstate/a2a/releases/download/v1/AIStudio2API.zip" -OutFile $ZipFile -UseBasicParsing
```

*(Optional integrity check: verify SHA-256 equals `9b6856b419b42bb93b628bd6381bef5970fbf2d305fb983d6564e749d6e75aee` via `sha256sum AIStudio2API.zip` on Linux, `shasum -a 256 AIStudio2API.zip` on macOS, or `(Get-FileHash $ZipFile -Algorithm SHA256).Hash.ToLower()` on Windows.)*

---

### Step 2: Unzip the Archive & Enter Extracted Folder

#### Linux / macOS
```bash
cd ~/a2a-pkg
unzip -q -o AIStudio2API.zip || python3 -m zipfile -e AIStudio2API.zip .
chmod +x AIStudio2API/linux/install-aistudio2api.sh AIStudio2API/macos/install-aistudio2api-macos.sh
cd ~/a2a-pkg/AIStudio2API
```

#### Windows (PowerShell)
```powershell
Expand-Archive -Path $ZipFile -DestinationPath $PkgDir -Force
Set-Location (Join-Path $PkgDir "AIStudio2API")
```

---

### Step 3: Read the Detailed README Inside & Execute Setup

From inside `AIStudio2API/`, open and follow **`README_AI_AGENT.md`**, which automatically routes by host OS:

| Host OS | Detailed AI Agent Guide (Inside ZIP) | Automated Installer Script (Inside ZIP) |
| :--- | :--- | :--- |
| **Universal Dispatcher** | `README_AI_AGENT.md` | Auto-routes to OS guide below |
| **Linux** (`x86_64` / `arm64`) | `linux/README_AI_AGENT.md` | `./linux/install-aistudio2api.sh` *(includes local `v0.3.10` `linux-amd64` archive)* |
| **macOS** (`arm64` / `x86_64`) | `macos/README_AI_AGENT.md` | `./macos/install-aistudio2api-macos.sh` |
| **Windows 10/11** (`x64`) | `windows/README_AI_AGENT.md` | `powershell -ExecutionPolicy Bypass -File .\windows\install-aistudio2api.ps1 -NoOpenUI` |

Full human documentation (`README.md`) and full git clones (`AIStudio2API-source/`, `magpie-gemini-web/`) are also inside the extracted folder.
