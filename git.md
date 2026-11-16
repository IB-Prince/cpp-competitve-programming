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
