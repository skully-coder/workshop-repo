# Workshop-Repo
This repo is to demonstrate the functions of Git and GitHub which were explained and discussed in a workshop of Github & Git.


## Some of the important points that were discussed in the workshop are listed below-   

1) Commits cannot be deleted because each commit’s hashcode is linked with previous hashcode

`git rm --cached Main.class`

cached means don’t delete the file, just remove it from staging area
last commit is HEAD

2) HEAD is a pointer pointer to commit

`git checkout master^ `(Head goes one step above)	(head will now point to previous commit)
// OR 
`git checkout HEAD^` 

`git checkout master~2		// goes above 2 commit wrt master`

   Master is always pointing at the leaf i.e. name of the branch always points at leaf node
   master means 'the project is stable and if we need to change we need to make another branch and change there'

3) git log shows files before HEAD

cat .git/HEAD (shows the commit id HEAD is currently pointing to)

git checkout master (comes down of commit)

4) `git log --oneline`
`git checkout 7adec83` (7adec83 : this is commit id)

`git branch` (shows all branches)
`git branch feature` (makes new branch feature) 
NOTE: * means HEAD is pointing where

NOW: 
`git checkout feature`
now * will be on feature, hence we can make changes

`git commit -m “something”`
We can add a message while committing to tell the changes made by us in a particular branch

`git checkout master`
`git commit -m “master”`
now master will be in a new branch and feature will be on another branch

now suppose we are done with feature and we want to add them in main master branch

`git checkout master`
`git merge feature`

new branch will be created with and it will be master branch

4) merge conflicts: 2 people made changes in same file in same line

then we need to manually choose which commit we want to choose. 
git merge feature


## Intermediate Level Git Commands
These Git commands are super helpful if you need to collaborate with your team, share your code with others at the intermediate level.

1) git remote
Git remote command acts like a border, and If you need to connect with the outside world, you have to use the Git remote command. This command will connect your local repository to the remote. 

Usage 

$ git remote add <shortname> <url>


Example

` git remote add origin https://dev.azure.com/aCompiler/_git/DemoProject`



2) git push
Once you are connected with the remote repository (with the help of the git remote command), it's time to push your changes to that repository.

Usage 

$ git push -u <short_name> <your_branch_name>

Example 

`git push -u origin feature_branch`


You should have origin and upstream set up before you use Git push. And here is the command to set up upstream.

Usage 

$ git push --set-upstream <short_name> <branch_name>

Example 

`git push --set-upstream origin feature_branch`



3. git fetch 
When you need to download other team members' changes, you have to use git fetch. 

This command will download all information for commits, refs, etc., so you can review it before applying those changes in your local repository.

Usage 

`git fetch` 


4. git pull
The Git pull command downloads the content (and not the metadata) and immediately updates your local repository with the latest content. 

Usage 

`git pull <remote_url>`



5. git stash
This Git command temporarily stores your modified files. You can work in stashed with the following Git command. 

Usage 

`git stash`

And you can view all of your stashes with the following command 

`git stash list`

And if you need a apply a stash to a branch, simply use apply 

`git stash apply` 



6. git log
With the help of the Git log, you can see all the previous commits with the most recent commit appear first.

Usage 

`git log` 

By default, it will show you all the commits of the currently checked out branch, but you can force it to see all the commits of all the branches with all options. 

`git log --all`



7. git shortlog
The shortlog command shows you a summary from the Git log command. This command is helpful if you are just interested in the short summary. 

This command is helpful to see who worked on what as it group author with their commits.

Usage 

`git shortlog`  

Git Shortlog Results


8. git show
Compared to the Git log, this command git show will show you details about a specific commit.

Usage 

`git show <your_commit_hash>`



9. git rm
Sometimes you need to delete files from your codebase, and in that case, you can use the Git rm command.

It can delete tracked files from the index and the working directory.

Usage 

   `git rm <your_file_name>`



10. git merge
Git merge helps you to integrate changes from two branches into a single branch. 

Usage 

`git merge <branch_name>`

This command will merge the <branch_name> into your current selected branch.


