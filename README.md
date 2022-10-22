# workshop-repo
This repo is to demonstrate the functions of Git and GitHub


#Some of the important points that were discussed in the workshop are listed below-   

1) commits cannot be deleted because each commit’s hashcode is linked with previous hashcode

git rm --cached Main.class

cached means don’t delete the file, just remove it from staging area
last commit is HEAD

2) HEAD is a pointer pointer to commit

git checkout master^ (Head goes one step above)	(head will now point to previous commit)
// OR 
git checkout HEAD^ 

git checkout master~2		// goes above 2 commit wrt master

master is always pointing at the leaf i.e. name of the branch always points at leaf node
master means the project is stable and if we need to change we need to make another branch and change there

3) git log shows files before HEAD

cat .git/HEAD (shows the commit id HEAD is currently pointing to)

git checkout master (comes down of commit)

4) git log --oneline
git checkout 7adec83 (7adec83 : this is commit id)

git branch (shows all branches)
git branch feature (makes new branch feature) 
NOTE: * means HEAD is pointing where

NOW: 
git checkout feature
now * will be on feature, hence we can make changes

git commit -m “something”
git commit -m “something”
git commit -m “something”

git checkout master
git commit -m “master”
now master will be in a new branch and feature will be on another branch

now suppose we are done with feature and we want to add them in main master branch

git checkout master
git merge feature

new branch will be created with and it will be master branch

4) merge conflicts: 2 people made changes in same file in same line

then we need to manually choose which commit we want to choose. 
git merge feature...