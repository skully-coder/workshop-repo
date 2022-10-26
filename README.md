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
git merge feature...


## Advanced Level Git Commands
And now the time to up one more level. In this section, you will learn the advanced Git commands. These commands will take time and practice.

Once you know the basics of these commands, it will be easy to use them every day.

1. git rebase 
Git rebase similar to the git merge command. It integrates two branches into a single branch with one exception. A git rebase command rewrites the commit history.

You should use the Git rebase command when you have multiple private branches to consolidate into a single branch. And it will make the commit history linear.

Usage 

`$ git rebase <base>`



2. git bisect 
The Git bisect command helps you to find bad commits. 

Usage

i) To start the git bisect 

`$ git bisect start`


ii) let git bisect know about a good commit

`$ git bisect good a123` 


iii) And let git bisect know about a bad commit

`$ git bisect bad z123`

With Git bisect you can narrow down the broken code within a few minutes.


3. git cherry-pick 
Git cherry-pick is a helpful command. It's a robust command and allows you to pick any commit from any branch and apply it to any other branch.

Usage

`$ git cherry-pick <commit-hash>`

Git cherry-pick doesn’t modify the history of a repository; instead, it adds to the history.



4. git archive 
Git archive command will combine multiple files into a  single file. It's like a zip utility, so it means you can extract the archive files to get individual files.

Usage 

`$ git archive --format zip HEAD > archive-HEAD.zip`

It will create a zip archive of the current revision.



5. git pull --rebase
Most of the time, you need to do rebase (and no merge) when you use Git pull.

In that case, you can use the option

Usage

`$ git pull --rebase`

It will help you to keep the history clean. Also, you can avoid multiple merges.



6. git blame 
If you need to examine the content of any file line by line,  you need to use git blame. It helps you to determine who made the changes to a file.

Usage 

`$ git blame <your_file_name>`



7. git tag
In Git, tags are helpful, and you can use them to manage the release. You can think of a Git tag like a branch that will not change. It is significantly more important if you are making a public release.

Usage 

`$ git tag -a v1.0.0`


8. git verify-commit
The git verify-commit command will check the gpg signature. GPG or “GNU Privacy Guard” is the tool used in sign files and contains their signatures.

Usage 

`$ git verify-commit <commit>`



9. git verify-tag
In the same way, you can confirm a tag.

Usage 

`$ git verify-tag <tag>`


10. git diff
Most of the time, you need to compare two git files or branches before you commit or push. Here is a handy command to do that. 

Usage

i) to compare the working directory with the local repo:

`$ git diff HEAD <filename>`

ii) to compare two branches:

`$ git diff <source branch> <target branch>`


