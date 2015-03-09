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
  * FEEC Can't use SSH. Use HTTS (`https://github.com/your_account/feec-git-flow.git`) instead.
  * Go to GitHub (`https://github.com/settings/applications#personal-access-tokens`) to generate for SourceTree if you use 2-Factor Authentication.
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

# Start Feature
1. back to SourceTree and click `Git Flow` on top menu
2. click `Start New Feature`, input `feature_1`, and choose `Lastest development branch`
3. see new branch `feature_1` in sourcetree
4. developing
  * add new file `feature_1.txt` in source path
  * input content `Test1` and commit
  * input content `Test22` and commit (demo hotfix later)
  * input content `Test3` and commit
5. finish feature
  * back to sourcetree, choose `feature\feature_1` 
  * click `Git Flow` on top menu -> `Finish Feature`
  * compare rebase effect (do not use rebase)
  * mention delete branch
  * auto merge to `develop` branch
  * checkout to `master` and compare content in source path
  * push to server

# Start Release
1. back to sourcetree and click `Git Flow` on top menu
2. click `Start New Release`, input `release_1`, and choose `Lastest development branch`
3. see new branch `release_1` in sourcetree
4. testing and fix bug
  * input content `Test4` in `feature_1.txt` and commit
  * input content `Test5` in `feature_1.txt` and commit
5. finish release
  * back to sourcetree and choose `release\release_1`
  * click `Git Flow` on top menu -> `Finish Release`
  * input tag `v0.1` to comment the release is version 0.1
  * mention: auto merge to `develop` and `master`
  * checkout to `master` and compare content in source path
  * push to server

# Start Hotfix
1. back to sourcetree and click `Git Flow` on top menu
2. click `Start New Hotfix` and input `bug1`
3. see new branch `bug1` in sourcetree
4. fix bug
  * open `feature_1.txt`, fix `Test22` to `Test2` and commit
5. finish hotfix
  * back to sourcetree and choose `hotfix\bug1`
  * click `Git Flow` on top menu -> `Finish Hotfix`
  * tag (option)
  * mention: auto merge to `develop` and `master`
  * checkout to `master` and compare content in source path
  * push to server

# Mix - Stash
1. start a Feature: `feature_2`
  * copy file `feature_1.txt` to `feature_2.txt`
  * input `Test2-1` in `feature_1.txt`
2. Bug happening and back to sourcetree, add stage changes, and click `Stash` on top menu
  * input `back_to_bug`
  * `stashes` in sourcetree
  * no `Test2-1` in `feature_1.txt` and `feature2.txt` will be not in source path.
3. Start a Hotfix: `bug2`
  * input `fix1` and `fix2` to `feature_1.txt` and commit `feature_1.txt`
4. Finish a Hotfix
  * mention: auto merge to `develop` and `master`
5. checkout to `feature_2` and merge `develop`
6. apply stash
7. add `Test2-2` in `feature_1.txt` and commit it
8. finish feature
9. start and finish release

# Mix - Commit
1. start a Feature: `feature_3`
  * copy file `feature_1.txt` to `feature_3.txt`
  * input `Test3-1` in `feature_1.txt`
2. Bug happening and back to sourcetree, commit current change
3. Start a Hotfix: `bug3`
  * input `fix3` and `fix4` to `feature_1.txt` and commit `feature_1.txt`
4. Finish a Hotfix
  * mention: auto merge to `develop` and `master`
5. checkout to `feature_3` and merge `develop`
6. finish the feature without rebase (rebase will be error)