# VSCode
VSCode is the most popular code editor globally. All code for SWE Fundamentals will be written using VSCode.
# Installation:
Download VSCode for your operating system [here](https://code.visualstudio.com/Download).

Required Software 2
This document outlines required software.

# [Windows Only] Install Windows-specific software
Install and setup Windows Subsystem for Linux (WSL)
WSL allows us to run the Linux operating system on Windows machines. We do this because most programming uses Unix-based operating systems, of which MacOS is a descendant. Most SWEs that use Windows do their work in WSL to maximise compatibility between their work and work done on Linux machines. Before installing WSL, update Windows to the latest version.

Install WSL [here](https://docs.microsoft.com/en-us/windows/wsl/install-win10).
Install the latest version of Ubuntu [here](https://apps.microsoft.com/store/detail/ubuntu-22041-lts/9PN20MSR04DW?hl=en-sg\&gl=sg). Ubuntu is a popular version of the Linux operating system.
Run sudo apt install build-essential in Ubuntu in WSL to install standard libraries Ubuntu needs to further install common packages.
Run sudo apt-get install ca-certificates in Ubuntu in WSL to get SSL verification certificates on Ubuntu for Ubuntu to communicate with VS Code on our computer.

# Integrate VS Code with WSL
Install the VS Code Remote Development [extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack) to enable VS Code to integrate with WSL.
Click the Remote Development extension icon in the bottom left corner of VS Code. A pop up will appear with a list of options. Click the first option "Remote-WSL: New Window" for the default distro.
You will see a notification "Starting VS Code in WSL...". This means VS Code is setting up a server inside WSL for the first time. Once installed, the VS Code of your Windows OS will sync automatically with the VS Code of your Ubuntu OS, and the VS Code terminal will show the Ubuntu terminal.

# Install Git
Windows
Open an Ubuntu terminal in VS Code and run the following commands separately.
```bash
sudo apt-get update

sudo apt-get install git
```

# Verify correct installation by checking Git version
```bash
git –version
```
# Personal Access Tokens
Configure Git and GitHub
When using the HTTPS protocol on GitHub to retrieve repository information you will need to develop a personal access token on your GitHub account, you will then be able to use this token to authenticate your request. To create a personal access token please follow this set of documentation.
After you have created the personal access token be sure to save it in a safe spot as it will be required when authenticating requests to the GitHub servers. You will be prompted to pass your GitHub username and password when trying to push to repositories, use your Personal Access Token in place of your password.

# Configure Git default branch
Set the default Git branch to main as per GitHub's latest convention. Some older versions of Git may still use master as the default branch name.
```bash
git config --global init.defaultBranch main
```

# Configure Git default editor
Follow instructions [here](https://stackoverflow.com/a/39604469) to enable the code command in terminal to open VS Code.
Set the default Git code editor to VS Code to avoid Git's default command line editor Vim, which req#uires learning Vim-specific keyboard shortcuts. We may need to use Vim on remote servers as SWEs, but to keep things simple during Bootcamp we will stick to VS Code.

```bash
git config --global core.editor "code --wait"
```

# Configure Git and GitHub Credentials
Set your GitHub account credentials on your computer through the command line. This will enable us to interact with GitHub via the command line, which we will do a lot. Please replace <YOUR_GITHUB_USERNAME> and <YOUR_GITHUB_EMAIL> with your GitHub username and email.
```bash
git config --global user.name "<YOUR_GITHUB_USERNAME>"

git config --global user.email "<YOUR_GITHUB_EMAIL>"
```


Type git config -l into the terminal to verify configuration success. If you see user.name and user.email in the output, we succeeded. If you see a : at the bottom of the output, you may need to press Enter until you see the lines starting with user.name and user.email.
After configuring your GitHub credentials you will be able to access GitHub repositories and make requests, however you will be prompted for your username and password every single request. 
While this level of security is brilliant for companies it can be frustrating for the developers. To make your lives a tad easier you can run these commands in your CLI in order to save your credentials into the environment.
```bash
git config --global credential.helper store

git config --global credential.helper cache
```

After doing these commands you may need to go through git flow once before it has saved your credentials (including your personal access token, which should be used as a password when prompted for username and password.


Once you have setup the above, goto [2BASIC.md](/2BASIC.md)