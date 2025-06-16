## Authentication

### GitHub CLI (Easiest method)
```sh
gh auth login
### Where do you use GitHub?
GitHub.com
### What is your preferred protocol for Git operations on this host?
HTTPS
### Authenticate Git with your GitHub credentials?
Y
### How would you like to authenticate GitHub CLI?
Login with a web browser
First copy your one-time code: XXXX-XXXX
Press Enter to open https://github.com/login/device in your browser...
```

## Config

### Email
`git config --global user.email "email-registered-on-git"`

### Username
`git config --global user.name "git-username"`

## Branch

### Create new
`git checkout -b <branch-name>`
Right after, needs to publish the branch, otherwise, branch will exist only locally
`git push -u origin <branch-name>`

### Switch branch
`git checkout <branch name>`

### See local branches
`git branch`

### See remove branches
`git branch -r`

### Delete branch
`git branch -D <branch-name>`

## Files

### Add/Stage files
`git add <file-name>`
You can also use the path of a folder for multiple files
`git add <path>`
You can also use . for all the files
`git add .`

### Commit files
`git commit -m '<message>`
You need to add a message, even if it is a dot (.)

## Push files
`git push`