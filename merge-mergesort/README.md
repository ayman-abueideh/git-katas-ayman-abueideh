# Git Kata: Merge Mergesort
In this kata you will be facing your first merge conflict!
There will be two different branches:

* Mergesort-Impl
* master

The task is to look at the merge conflict, and solve it by editing the file accordingly.

## Setup:

1. Run `source setup.sh` (or `.\setup.ps1` in PowerShell)

## The task

1. Run `git branch` to see the two branches present <br>

`  Mergesort-Impl
* master
`<br><br>

2. Merge `Mergesort-Impl` into `master`<br>

`Auto-merging mergesort.py
CONFLICT (content): Merge conflict in mergesort.py
Automatic merge failed; fix conflicts and then commit the result.
`<br><br>

3. Either:<br>
   1. Solve the merge conflict with your favorite editor and finish the merge (`git status` will tell you what to do), **or**<br>
   2. Use `git mergetool --tool=emerge` (for emacs fans) or `git mergetool --tool=vimdiff` (for vim fans) and finish the merge (`git status` will tell you what to do)<br>

## Relevant commands
- `git branch`
- `git merge`
- `git status`
- `git mergetool --tool=emerge`
- `git mergetool --tool=vimdiff`
- `git add`
- `git commit`

