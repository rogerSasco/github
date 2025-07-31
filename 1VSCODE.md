# VSCode
VSCode is the most popular code editor globally. All code for SWE Fundamentals will be written using VSCode.
# Installation:
Download [VSCode](https://code.visualstudio.com/Download) for your operating system [here](https://youtu.be/GAiaqN87Pp8?si=Zqj37lp-3DRT2wNG).

Required Software 2
This document outlines required software.

# [Windows Only] Install Windows-specific software
Install and setup Windows Subsystem for Linux (WSL)
WSL allows us to run the Linux operating system on Windows machines. We do this because most programming uses Unix-based operating systems, of which MacOS is a descendant. Most SWEs that use Windows do their work in WSL to maximise compatibility between their work and work done on Linux machines. Before installing WSL, update Windows to the latest version.

Install [WSL](https://docs.microsoft.com/en-us/windows/wsl/install-win10) [here](https://youtu.be/kGEDZzeZlj4?si=gf0zJ7j2g-K9Ptvx).
Install the latest version of [Ubuntu](https://apps.microsoft.com/store/detail/ubuntu-22041-lts/9PN20MSR04DW?hl=en-sg\&gl=sg) [here](https://youtu.be/hrBDFU6G-1M?si=vHvO0f1WjU6cb1Lt). Ubuntu is a popular version of the Linux operating system.
Run sudo apt install build-essential in Ubuntu in WSL to install standard libraries Ubuntu needs to further install common packages.
Run sudo apt-get install ca-certificates in Ubuntu in WSL to get SSL verification certificates on Ubuntu for Ubuntu to communicate with VS Code on our computer.

# Integrate VS Code with WSL
Install the VS Code Remote Development [extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack) to enable VS Code to integrate with WSL. Vial VS code [here](https://youtu.be/gdLyNIxbOxQ?si=IUmcKoikZvrgczQV).
Click the Remote Development extension icon in the bottom left corner of VS Code. A pop up will appear with a list of options. Click the first option "Remote-WSL: New Window" for the default distro.
You will see a notification "Starting VS Code in WSL...". This means VS Code is setting up a server inside WSL for the first time. Once installed, the VS Code of your Windows OS will sync automatically with the VS Code of your Ubuntu OS, and the VS Code terminal will show the Ubuntu terminal.

# Install Git
Windows
Open an Ubuntu terminal in VS Code and run the following commands separately.
```bash
sudo apt-get update

sudo apt-get install git
```
install Git video steps [here](https://youtu.be/ahobC1XzDno?si=w4NcB2biTx0E3Q2O)
# Verify correct installation by checking Git version
```bash
git –version
```
# SSH keys setup
GitHub, GitLab have implemented beyond password authenication, and the most secure way is SSH, PAT is for CI/CD production, SSH is for developers.
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```
Press Enter to accept defaults
```bash
cat ~/.ssh/id_ed25519.pub
```
Go to GitHub SSH Keys Settings → Add new key.
```bash
ssh -T git@github.com
```
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