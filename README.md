# Generate SSH Key
1. Windows Start -> Git -> Git Bash
2. Command: `ssh-keygen -t rsa` and enter for default
3. Execute Notepad to open `C:\Users\your_account\.ssh\id_rsa.pub` and copy all content
4. Go to GitHub: `https://github.com/settings/ssh` -> `Add SSH key` and paste pub key


# SourceTree Setting
1. Tools -> Option
2. Fill `FullName` and `Email address` for Git commit
3. Choose `C:\Users\your_account\.ssh\id_rsa` for SSH Key
4. Choose `OpenSSH` for SSH Client

# Create New Repository and Clone It
1. create new repository `test-git-flow` on GitHub
2. copy url like `git@github.com:your_account/test-git-flow.git`
3. 