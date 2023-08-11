# Git Kata: 3-Way Merge

## Setup

1. Run `source setup.sh` (or `.\setup.ps1` in PowerShell)

## The task

You again live in your own branch, this time we will be doing a bit of juggling with branches, to show how lightweight branches are in git.

1. Create a branch called greeting and switch to it :  ` git checkout -b "greeting"` <br>
2. Edit the greeting.txt to contain your favorite greeting <br>
3. Add greeting.txt files to the staging area : `git add .`  <br>
4. Commit: `git commit -m "edit greeting file"` <br>
5. Switch back to the master branch :`git checkout master` <br>
6. Create a file README.md with information about this repository: `touch README.md` <br>
7. Add the README.md file to staging area and make the commit <br>
8. What is the output of `git log --oneline --graph --all`?<br>

`* 0724c51 (HEAD -> master) add README.md
| * 30c78f5 (greeting) edit greeting file
|/
* bbbf935 Add content to greeting.txt
* 2de8223 Add file greeting.txt
`<br><br>

9. Diff the branches<br>

`diff --git a/README.md b/README.md
new file mode 100644
index 0000000..e69de29
diff --git a/greeting.txt b/greeting.txt
index b8b9887..ce01362 100644
--- a/greeting.txt
+++ b/greeting.txt
@@ -1 +1 @@
-hello Gaza Sky Geeks
+hello` <br><br>

10. Merge the greeting branch into master<br>

`git merge greeting
Merge made by the 'ort' strategy.
 greeting.txt | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
`<br><br>

11. What is the output of `git log --oneline --graph --all` now? Observe the extra merge commit created with the message "Merge branch 'greeting'".<br>

`git log --oneline --graph --all
*   dc2c4fc (HEAD -> master) Merge branch 'greeting' for testing
|\
| * 30c78f5 (greeting) edit greeting file
* | 0724c51 add README.md
|/
* bbbf935 Add content to greeting.txt
* 2de8223 Add file greeting.txt
`<br><br>

## Useful commands

- `git branch`
- `git branch <branch-name>`
- `git branch -d <branch-name>`
- `git switch <branch-name>`
- `git switch -c <branch-name>`
- `git branch -v`
- `git add`
- `git commit`
- `git commit -m`
- `git merge <branchA> <branchB>`
- `git diff <branchA> <branchB>`
- `git log --oneline --graph --all`
