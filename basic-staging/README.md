# Git Kata: Basic Staging

This kata will examine the staging area of git.

In git we are working with three different areas:

* The working directory where you are making your changes
* The staging area where all changes you have added through `git add` will stay
* The repository where every commit ends up, making your history. To put your staged changes in here you issue the `git commit` command.

A file can have changes both in the working directory and staging area at the same time.
These changes do not have to be the same.

We will also work with `git restore` to restore the staged changes of a file, and `git checkout` to return a file to a previous state.

## Setup

1. Run `source setup.sh` (or `.\setup.ps1` in PowerShell)

## The task

You live in your own repository. There is a file called `file.txt`.

1. What's the content of `file.txt`? `1`
2. Overwrite the content in `file.txt`: `echo 2 > file.txt` to change the state of your file in the working directory (or `sc file.txt '2'` in PowerShell)
3. What does `git diff` tell you?

`
diff --git a/file.txt b/file.txt
index d00491f..0cfbf08 100644
--- a/file.txt
+++ b/file.txt
@@ -1 +1 @@
-1
+2
`
4. What does `git diff --staged` tell you?  why is this blank? ` it prints nothing because nothing added to the stage area`
5. Run `git add file.txt` to stage your changes from the working directory.
6. What does `git diff` tell you? ` nothing `
7. What does `git diff --staged` tell you?

`
diff --git a/file.txt b/file.txt
index d00491f..0cfbf08 100644
--- a/file.txt
+++ b/file.txt
@@ -1 +1 @@
-1
+2
`

8. Overwrite the content in `file.txt`: `echo 3 > file.txt` to change the state of your file in the working directory (or `sc file.txt '3'` in PowerShell).
9. What does `git diff` tell you?

`
diff --git a/file.txt b/file.txt
index 0cfbf08..00750ed 100644
--- a/file.txt
+++ b/file.txt
@@ -1 +1 @@
-2
+3
`

10. What does `git diff --staged` tell you?

`
diff --git a/file.txt b/file.txt
index d00491f..0cfbf08 100644
--- a/file.txt
+++ b/file.txt
@@ -1 +1 @@
-1
+2
`

11. Explain what is happening ` when we run git diff it compares the changes with the staging area but when we add -- staging it compares staging changes with the latest commit changes`
12. Run `git status` and observe that `file.txt` are present twice in the output. `correct it appeared twice`
13. Run `git restore --staged file.txt` to unstage the change
14. What does `git status` tell you now?

`
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   file.txt
`
15. Stage the change and make a commit
16. What does the log look like?

`
git commit -m "add file.txt"
[master df05cae] add file.txt
 1 file changed, 1 insertion(+), 1 deletion(-)
`

17. Overwrite the content in `file.txt`: `echo 4 > file.txt` (or `sc file.txt '4'` in PowerShell)
18. What is the content of `file.txt`? `4`
19. What does `git status` tell us?

`
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   file.txt

no changes added to commit (use "git add" and/or "git commit -a")
`

20. Run `git restore file.txt`
21. What is the content of `file.txt`? `3`
22. What does `git status` tell us? `nothing`

## Useful commands

- `git add`
- `git commit`
- `git commit -m "My lazy short commit message"`
- `git log`
- `git log -n 5`
- `git log --oneline`
- `git log --oneline --graph`
- `git restore --staged`

## Aliases

You can set up aliases as such:
`git config --global alias.lol 'log --oneline --graph --all'`
This might be useful to you.
