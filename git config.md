# Setting up Git Credential commands

1. Enter the username User Name
```
git config --global user.name "username"
```

2. Enter the user email id
```
git config --global user.email "username@gmail.com"
```
3. To verify the current configs
```
git config -l
```
4. To capture and cahce the password next time it is entered

```
git config --global credential.helper cache
```
5. Just do git pull pr push  and enter the token

6. To delete branch locally.
```
git branch -d localBranchName
```

7. To create new branch 
```
git checkout -b branchName
# Publishing after commit
git push --set-upstream origin dn
```

8. Remove local changes

If you mean you want the pull to overwrite local changes, doing the merge as if the working tree were clean, well, clean the working tree:

```
git reset --hard
git pull
```
If there are untracked local files you could use git clean to remove them.
```
git clean -f to remove untracked files
```
-df to remove untracked files and directories
-xdf to remove untracked or ignored files or directories

If on the other hand you want to keep the local modifications somehow, you'd use stash to hide them away before pulling, then reapply them afterwards:
```
git stash
git pull
git stash pop
```
I don't think it makes any sense to literally ignore the changes, though - half of pull is merge, and it needs to merge the committed versions of content with the versions it fetched.

10. Undo Git Add using restore
The easiest way to undo your git add command is to use the “git restore” command with the “–staged” option and specify the file you want to unadd.
```
$ git restore --staged <file>
```
11. To show your Git credentials is with this git config command

```
git config --list
```
12. Password Unser
```
git config --global --unset user.password
```
13. Git cleaning untracked files
```
git clean -f -x
```
