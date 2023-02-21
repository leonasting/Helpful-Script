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
```

