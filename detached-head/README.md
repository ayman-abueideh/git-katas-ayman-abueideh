# Detached head state

When a user ends up in a "detached head" state, this is a scary situation, but as we know, Git is not scary.

## Setup:

1. Run `source setup.sh` (or `.\setup.ps1` in PowerShell)

## The task

1. Run `git status` and `git log --oneline --graph --all` to see what is going on.<br><br>

`
git status
HEAD detached at e55317d

 git log --oneline --graph --all
* f7620ad (master) D
* 094df57 C
* ce40d8c B
* e55317d (HEAD) A

`
<br><br>
2. Restore normalcy in this repository by moving to `master` `using git checkout master`<br><br>

Note that this task might seem more confusing if you did not run `setup.sh` in your terminal.<br><br>

We want to have a branch called `the-beginning` that is made from the first commit with message `A`.<br><br>

3. Can you do this by first causing a detached head?<br><br>

`
1- git checkout e55317d
2- git checkout -b "the-beginning"
`<br><br>

## Useful commands

- `git status`
- `git log --oneline --graph --all`
- `git checkout <ref>` or `git switch --detach <ref>`
