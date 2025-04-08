*Challenge 1: Perform an interactive rebase to modify commit history (rename, squash, reorder commits):

mkdir challenge-1 as create a folder (or) directory

cd challenge-1 as to change the directory

git init to intialize the git and .git file has been created

1.create and commit 4 files:

touch challenge-1.txt to create a file

git add challenge-1.txt "challenge-1 added" to added the file

git commit -m "challenge-1 added" to commit the file

touch challenge-2.txt to create a file

git add challenge-2.txt "challenge-2 added" to added the file

git commit -m "challenge-2 added" to commit the file

touch challenge-3.txt to create the file

git add challenge-3.txt to added the file

git commit -m "challenge-3 added" to commit the file

touch challenge-4.txt to create the file

git add challenge-4.txt to added the file

git commit -m "challenge-4 added" to commit the file

2. check the commit history:

git log --oneline to check the commited files

93e37e1 (HEAD -> master) challenge-4 added
7bb847e challenge-3 added
25e19af challenge-2 added
428ab0d challenge-1 added

3. Start an Interactive Rebase:

if We want to edit the last 4 commits

git rebase -i HEAD~4

If you ever want to rebase all the way from the first commit, you can do this:

git rebase -i --root

pick 428ab0d challenge-1 added
pick 25e19af challenge-2 added
pick 7bb847e challenge-3 added
pick 93e37e1 challenge-4 added


*Challenge 2: Use git cherry-pick to apply a specific commit from another branch to your current branch:

step by step:

step-1:

mkdir challenge-2                  (to create a folder or directory)

step-2

cd challenge-2                     (to change the directory)

step-3:

git init                          (to intialize the .git file)

step-4:

touch challenge-1.txt challenge-2.txt

step-5:

add and commit files:

git add challenge-1.txt

git commit -m "challenge-1 added"

git add challenge-2.txt

git commit -m "challenge-2 added"

Create and switch to dev branch:

git checkout -b "dev"

create two files

touch master1 dev1

commit the two files:

git add master1

git commit -m "master1 added"

git add dev1

git commit -m "dev1 added"

check git log:

 git log --oneline
290ec24 (HEAD -> dev) dev1 added
f2f33dc master1 added
a7b3608 (master) challenge-2 added
3ac51e9 challenge-1 added

Switch to master branch:

git checkout master

git cherry pick:

 git cherry-pick 290ec24
[master 67cb226] dev1 added
 Date: Mon Apr 7 11:27:27 2025 +0530
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 dev1

*Challenge 3: Create a merge conflict scenario and manually resolve it using git merge and git rebase:

mkdir challenge-3            (To create the folder or directory)

cd challenge-3                (To change the directory)

git init                       (To intialize the .git file)

touch challemge-1              (To create a file )

git add challenge-1            (To add the file)

git commit-m "challenge-1 added"

touch master1

git add master1

git commit -m "master1 added"

touch master2

git add master2

git commit -m "master2 added"

git checkout -b master10

touch feature

git add feature

git commit -m "feature added"

$ git log --oneline --graph --all --date-order
* c61d8e0 (HEAD -> master10) feature1 added
| * 0b21349 (master) feature1 added
* | 2967d18 feature addded
|/
* e12da9d master2 added
* d4d42c2 master1 added
* cf6e8d9 challenge-1 added

git checkout master     (To switch the master)

$ git log --oneline
0b21349 (HEAD -> master) feature1 added
e12da9d master2 added
d4d42c2 master1 added
cf6e8d9 challenge-1 added

git merge master10

$ git merge master10
Merge made by the 'ort' strategy.
 feature | 0
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 feature

 $ git log --oneline
2392687 (HEAD -> master) Merge branch 'master10'
c61d8e0 (master10) feature1 added
0b21349 feature1 added
2967d18 feature addded
e12da9d master2 added
d4d42c2 master1 added
cf6e8d9 challenge-1 added


$ git log --oneline --graph --all --decorate --date-order
*   2392687 (HEAD -> master) Merge branch 'master10'
|\
| * c61d8e0 (master10) feature1 added
* | 0b21349 feature1 added
| * 2967d18 feature addded
|/
* e12da9d master2 added
* d4d42c2 master1 added
* cf6e8d9 challenge-1 added


Challenge-4: Undo a commit using git reset (soft, mixed, and hard) and git revert – understand the differences:

mkdir challenge-4                    (To create a folder or directory )

cd challenge-4                       (To change directory as challenge-4)

touch file-a.txt                (To create the file)

git add file-a.txt               (To add the file)

git commit -m "file-a.txt added"

touch file-b.txt                (To create the file)

git add file-b.txt               (To add the file)

git commit -m "file-b.txt added"

touch file-c.txt                (To create the file)

git add file-c.txt               (To add the file)

git commit -m "file-c.txt added"

touch file-d.txt                (To create the file)

git add file-d.txt               (To add the file)

git commit -m "file-d.txt added"

$ git log --oneline
bd2dad9 (HEAD -> master) file-d.txt added
92f8172 file-c.txt added
cf07444 file-b.txt added
d76b34b file-a.txt added

$ git reflog
9fcdd75 (HEAD -> master) HEAD@{0}: commit: file-d.txt added
92f8172 HEAD@{1}: reset: moving to HEAD~1
bd2dad9 HEAD@{2}: commit: file-d.txt added
92f8172 HEAD@{3}: commit: file-c.txt added
cf07444 HEAD@{4}: commit: file-b.txt added
d76b34b HEAD@{5}: commit (initial): file-a.txt added































   













