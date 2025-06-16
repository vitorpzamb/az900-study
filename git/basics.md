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