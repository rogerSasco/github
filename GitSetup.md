The error **`git is not recognised as a cmdlet`** typically occurs in **PowerShell** when Git is either not installed or not properly added to the system's **PATH environment variable**. Here’s how to fix it:

---

### **1. Check if Git is Installed**
Run this command in **PowerShell** or **Command Prompt**:
```sh
git --version
```
- If Git is installed, it will show the version (e.g., `git version 2.40.0`).  
- If not, you’ll see an error.

---

### **2. Install Git (If Missing)**
Download and install Git from the official website:  
👉 [https://git-scm.com/downloads](https://git-scm.com/downloads)  

**During installation:**  
- Ensure you check **"Add Git to PATH"** (critical for PowerShell to recognize `git`).  
- Restart your terminal after installation.

---

### **3. Verify Git is in PATH**
Run in PowerShell:
```sh
$env:Path
```
Check if Git’s `bin` directory (e.g., `C:\Program Files\Git\bin`) is listed.  
If not, add it manually:
```sh
[System.Environment]::SetEnvironmentVariable("Path", "$env:Path;C:\Program Files\Git\bin", "User")
```
Restart PowerShell.

---

### **4. Alternative: Use `git.exe` Explicitly**
If PATH issues persist, try:
```sh
& "C:\Program Files\Git\bin\git.exe" --version
```

---

### **5. Reinstall Git (If Still Broken)**
Uninstall Git via **Settings > Apps**, then reinstall it with PATH enabled.

---

### **Why This Happens**
- PowerShell uses **cmdlets** (like `Get-ChildItem`), but `git` is a standalone executable.  
- If Git’s path isn’t in `$env:Path`, PowerShell won’t recognize it.

Let me know if you need further help! 🚀