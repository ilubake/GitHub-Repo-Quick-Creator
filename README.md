# New_GitHubRepo.bat
A Windows batch script to **one-click create private GitHub repositories and clone them locally**, eliminating manual operations like web-based repo creation, Git initialization, and CLI command execution.  
（Windows批处理脚本，一键创建私有GitHub仓库并完成本地克隆，省去手动网页创仓、Git初始化、CLI命令执行等繁琐操作。）

## 📋 Environment Requirements（环境要求）
| Dependency       | Requirement                                                                 | Installation Guide                                                                 |
|------------------|-----------------------------------------------------------------------------|-----------------------------------------------------------------------------------|
| Operating System | Windows (7/10/11)                                                           | -                                                                                 |
| Git              | Installed and added to system PATH                                          | Download: [Git for Windows](https://git-scm.com/download/win)                     |
| GitHub CLI       | Installed and added to system PATH                                          | Install via: `winget install --id GitHub.cli`                                      |
| GitHub Auth      | Logged in to GitHub via `gh auth login` (personal access token/SSH/ browser) | Run `gh auth login` and follow the prompts to complete authentication              |

## 🚀 Usage（使用方法）
### Step 1: Get the script
Download `New_GitHubRepo.bat` to any local directory (e.g., `D:\Scripts\`).

### Step 2: Run the script
Double-click `New_GitHubRepo.bat` (or run it via Command Prompt/PowerShell).

### Step 3: Follow the prompts
1. The script will automatically check Git/GitHub CLI installation and GitHub login status.  
2. When prompted, enter a **valid repo name** (supports letters, numbers, hyphens, underscores; cannot be empty).  
3. Wait for the script to create the private repo on GitHub and clone it to the current directory.

### Step 4: Success confirmation
If successful, the script will:
- Show the local folder path (e.g., `C:\Your\Path\Your_Repo_Name`).
- Automatically enter the cloned repo directory.
- Prompt "Ready to start coding!".

## 📌 Core Features（核心功能）
| Feature                          | Description                                                                 |
|----------------------------------|-----------------------------------------------------------------------------|
| Auto Dependency Check            | Verifies Git/GitHub CLI installation; exits with error prompts if missing   |
| Login Status Validation          | Checks GitHub CLI authentication status; prompts login if not authenticated  |
| Repo Name Validation             | Ensures the input name is not empty (basic format check for valid characters)|
| One-Click Create & Clone         | Creates a private GitHub repo and clones it to the local directory via `gh`  |
| Clear Feedback                   | Shows success/error messages, possible failure reasons, and local path      |

## 🛠️ Future Update Roadmap（后续更新方向）
### 1. Enhanced Customization
- [ ] Support creating **public repositories** (add a prompt to select repo visibility: private/public).
- [ ] Allow custom repo descriptions (add input for `--description` parameter in `gh repo create`).
- [ ] Support custom local clone paths (let users specify where to clone the repo, instead of the current directory).

### 2. Robust Error Handling
- [ ] Add retry logic for network failures (e.g., retry 2-3 times if repo creation fails due to network issues).
- [ ] More detailed name validation (e.g., block special characters like spaces/symbols, check GitHub repo name rules).
- [ ] Auto-detect duplicate repo names (query GitHub first to avoid creation failures).

### 3. Usability Improvements
- [ ] Add multi-language support (switch between Chinese/English prompts).
- [ ] Auto-initialize repo with common files (e.g., `README.md`, `.gitignore`, `LICENSE`).
- [ ] Support batch creation (input multiple repo names to create/clone in bulk).
- [ ] Add parameterized execution (run the script with arguments like `New_GitHubRepo.bat my-repo --public` to skip interactive input).

### 4. User Experience
- [ ] Add progress bar/loading hints during repo creation/cloning.
- [ ] Option to open the cloned folder in File Explorer after success.
- [ ] Log file generation (record creation history, errors, and paths for troubleshooting).

### 5. Compatibility
- [ ] Add support for non-Winget environments (provide alternative GitHub CLI installation links).
- [ ] Compatibility with Git Bash/PowerShell Core.

## ⚠️ Notes（注意事项）
1. **Repo Name Rules**: GitHub repo names cannot contain spaces, slashes, or special characters (the script currently only checks for empty names; avoid invalid characters manually).
2. **Duplicate Names**: If the repo name already exists in your GitHub account, creation will fail (check your GitHub repo list first).
3. **Network Issues**: Ensure stable network connectivity (GitHub CLI requires internet access to create/clone repos).
4. **Permissions**: Run the script with normal user permissions (administrator rights are not required unless Git/GitHub CLI are installed in restricted directories).
5. **GH CLI Version**: Ensure you have the latest GitHub CLI version (old versions may have compatibility issues with `gh repo create`).

## ❓ Troubleshooting（常见问题）
| Error Message                                  | Solution                                                                 |
|------------------------------------------------|--------------------------------------------------------------------------|
| `Git not found`                                | Install Git from [git-scm.com/download/win](https://git-scm.com/download/win) and restart the script |
| `GitHub CLI not found`                         | Run `winget install --id GitHub.cli` or download from [GitHub CLI](https://cli.github.com/) |
| `Not logged in`                                | Run `gh auth login` in Command Prompt/PowerShell and complete authentication |
| `Creation failed (repo name already exists)`   | Use a new repo name or delete the existing repo on GitHub                |
| `Network issue`                                | Check internet connection, retry the script, or switch to a stable network |

## 📄 License
This script is provided "as is" without warranty of any kind. You are free to modify and distribute it for personal/non-commercial use.
