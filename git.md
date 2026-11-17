# Annotated Tagging

cmd:

git tag (to see the tags)
git log (to see all the commits)
git log --pretty=oneline

git tag -a v1.0 -m "1st release"

after commiting updates,
upload it including the tags on github repo:
git push origin v1.0

# Lightweight Tagging

460. Git branch create
     There are two options for branching
     1 - checkout
     new 2 - switch

both are ok. I think switch is much better.

git checkout feature1

to create new branch

- git checkout -b feature1 / - git switch -c branchName / - git switch --create branchName

to see all branches

- git branch ( for seeing local branches)
- git branch --all (for seeing local & remote branches)

switch betwee branches

- git checkout branchName / - git switch branchName

- git switch - (to go to previous branch)

461. Git delete branch

- git branch -d feature2 (branchName)

462. Git branch pushing to remote repository

- git push origin branchName

463. Git branch how it works

every time you do the commits by default it goes to main branch.
git commit takes a snapshot of your files, gives a hexacode for commit and a pointer.
About the pointer: - git log
shows (HEAD -> (to which branch. it points to your commits))
it has a parent, has a checksum and multiple things.

- git log --graph

(installed extension - git graph)

464. Git merge

I want to merge two branch. basically there're two ways of doing it.
1 - rebase
2 - merge
let's focus on merge now.
to use merge, you have to be on the main branch

- git merge branchName

465. Git rebase

working on multiple branches and merging them can make it complicated to understand during checking the history. That's where rebase comes in.

- git rebase feature3 (branchName)

If you want it to be clean to see in git graph the commits, go with rebase.
But if you really want to know what's happening with every branch, use git merge

466. Merge Conflict

- git merge feature3

-> conflict is caught when modified same file in two different branches.
You can check the difference by - git diff

just delete the things you need to erase to avoid conflict, save it, then add and commit.
vola! the merging is complete.

-> now, let's say, the remote repository has different codes, your local repo has different code in the same file. in that case, add, commit and then try to pull the code from remote github repo, you'll get a conflict.
resolve it, add, commit.

467. Git time travel
     you can see different commits checking git log. and if you want to
     go back to a particular commit - copy the commit id, git checkout paste_commit_id
     let's say you're working on a product, you want to make a light version of it by changing that best commit you had, name it lite-version:
     git checkout -b lite-version
     you'll see that as different branch now. (git branch)
     make your changes, do git add, commit, then git push origin lite-version
     now, you'll see a new branch lite-version with the modification.

468. Git stash
     I'm working on a feature that'd take sometimes let's say - 2 weeks.
     And in the middle, another bug from previous work was identified and need to fix
     right now. In that case if you try to switch to that branch it'll tell you to commit or stash. git stash saves the work without commiting. so, whenever you're comming back to this branch, you can continue working on it.
     git stash
     git stash list - give you the stash list
     git stash apply - give you the code to continue
