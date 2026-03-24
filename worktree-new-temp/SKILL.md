---
name: worktree-new-temp
description: Create new worktree and then a claude session in there.
effort: low
---

if user doesn't provide a name, ask for one and run the below two commands to create worktree for the user. otherwise just use the name in below command.

`git worktree add .claude/worktrees/{{name}} HEAD`

after the worktree created, run new session in new tmux window in current tmux session
`cd .claude/worktrees/{{name}} && claude`
