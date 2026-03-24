---
name: worktree-remove-temp
description: Remove existing worktree.
effort: low
---

if user doesn't provide a name for the target worktree and current session is inside a worktree, suggest the user to run this skill in a session in the root directory and ask if they still want to continue or stop here. if they still want to continue, notice them they might see a few errors after the worktree is removed.

if user provided a name and:

1. current session is inside another worktree, `cd` back to root directory before continue below
2. current session is not inside a worktree, just continue below

first check if the current session is running inside the target worktree's directory. if so, `cd` back to root directory after `git worktree remove` before running any other commands

run the command below to remove an existing worktree

`git worktree remove .claude/worktrees/{{tree_name}}`

if the worktree has changes, ask the user if they want to discard them, if yes, run following command

`git worktree remove --force .claude/worktrees/{{tree_name}}`

if the worktree folder is already not there, inform the user that the worktree does not exist and run the below command to show user what worktrees are available now

`git worktree list`
