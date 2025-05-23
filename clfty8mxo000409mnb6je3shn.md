---
title: "Git Commands"
datePublished: Wed Mar 29 2023 17:16:50 GMT+0000 (Coordinated Universal Time)
cuid: clfty8mxo000409mnb6je3shn
slug: git-commands
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/wX2L8L-fGeA/upload/b6d3542e52fa1dd9ea45c56f4a1318cf.jpeg

---

**Conventions**  
`<NEW_BRANCH_NAME>` = New branch name  
`<BRANCH_NAME>` = Current branch name  
`<COMMIT_MESSAGE>` = Message for commit/Description of changes/Message will be shown in Git.  
`<SOURCE_BRANCH_NAME>` = The branch which you want to merge  
`<COMMIT_CODE>` = Every commit will be assigned a unique commit code.

**Branch Creation**  
`git branch <NEW_BRANCH_NAME>`  
`git checkout <NEW_BRANCH_NAME>`  
OR  
`git checkout -b <NEW_BRANCH_NAME>`

**Switching to a branch**  
`git checkout <BRANCH_NAME>`  
OR  
`git switch <BRANCH_NAME>`

**Pull Latest Code**  
`git pull origin <NEW_BRANCH_NAME>`  
OR  
`git pull`

**Stash changes in the Branch**  
`git stash`  
Use the below command to get the changes back to the branch.  
`git stash pop`

**Upload Code**  
`git add .`  
`git commit -m "<COMMIT_MESSAGE>"`  
`git push origin <BRANCH_NAME>`

**Merging**  
`git merge <SOURCE_BRANCH_NAME>`

**Revert changes**  
`git revert -m 1 <COMMIT_CODE>`

**Delete local branch**  
`git branch -d <BRANCH_NAME>`

**Remove committed changes from PR or Branch**  
`git reset --soft Head~1`  
`git reset HEAD .idea/`  
`git commit -m ".idea folder ignored"` -&gt; `".idea folder ignored"` is commit message  
`git push origin <BRANCH_NAME> -f`

**Remove the committed file from local changes**

`git reset HEAD path/to/unwanted_file`

**Remove the committed files from the commit**  
`git rm --cached <file>`  
`git commit --amend`  
`# Examples`  
`git rm --cached "30-seconds.txt"`  
`git commit --amend`  
`# Removes 30-seconds.txt from the last commit`

**Rename the local branch**  
`git branch -m <NEW_BRANCH_NAME>`

**To get all remote branches to the local**  
`git fetch`

**Updating the git configurations**  
`git config`[`user.name`](http://user.name)`<USER_NAME>`  
`git config`[`user.email`](http://user.email)`<USER_EMAIL>`

**Update .gitignore file:**  
\- Make changes in the .gitignore file.  
\- Run `git rm -r --cached .` command. /  
\- Run `git add .` command and `git commit -m "Commit message"` or just `git commit` or continue working. What is really important here is step 2. And remember to just run `git add .` the command before doing any commit.

**Changing Your Repo's Language in GitHub:** Please refer to the below link for more information on this topic.  
[https://dev.to/katkelly/changing-your-repo-s-language-in-github-5gjo](https://dev.to/katkelly/changing-your-repo-s-language-in-github-5gjo)

**Git Worktree:** Refer to the video below for more information.  
[https://www.youtube.com/watch?v=ntM7utSjeVU](https://www.youtube.com/watch?v=ntM7utSjeVU)  
`git worktree add ../<FOLDER_NAME> <BRANCH_NAME>`  
`git worktree remove .`

Stay tuned... I'll update this post with more commands later 👋