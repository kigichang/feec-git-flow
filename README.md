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
3. SourceTree -> Clone/New -> paste url in `Source Path / URL` and change Destination Path (Option)

# First Commit and Push
1. create new file `README.md` in source path
  * add content `# This is a Git Flow Test #`
2. commit file
  * Back to SourceTree
  * check in README.md
  * `Commit` on left-top
  * Enter Comment `Init`
  * `commit` on right-bottom
3. push to server
  * `Push` on Top-Menu
  * click master and check Remote branch `master`
4. Go to GitHub and see the `README.md`

# Initialize GitFlow
1. back to SourceTree
2. `Git Flow` on Top-Menu
3. Use all default settings and click `ok`
4. current branch is `develop` on sourcetree
5. push `develop` to server
  * `Push` on top menu
  * click `develop` and check Remote branch `develop`
6. See `develop` branch on GitHub