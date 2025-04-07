Challenge-1:

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




   













