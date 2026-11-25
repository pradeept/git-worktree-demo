# README for Worktrees


This change is done in main worktree
This is a conflicting change
This change is done in new-feature worktree


---

## Git Worktrees

#### What is the Need?

Scenario: 
1) Imagine you are working on a new feature called auth in feature/auth branch, and you suddenly have to switch to main to hot fix some prod issue.

2) You want to work on multiple features at a time given the capabilities of AI, If you start an agent on feature/auth branch to implement auth system and switch to main branch to do something, the agent (working on auth) will suddenly see different files! THAT'S VERY BAD.

Old way: `git stash` the current changes in feature/auth and switch over to main to hot fix or work on something quick, switch back and do `git stash pop`. Which is tedious and doesn't work for 2nd scenario.

New way: Use git worktrees. You basically create a replica of your project on disk AND ALSO you share the same .git folder. Which allows us to look at branches in other worktress and even merge them.

__SO?__ 

So, no need to duplicate manually and struggle with `git fetch` to get the remote branches. No hassle of pushing duplicate repo changes and merging.... etc...

### Common Commands

- Create a worktree with a new branch 

`git worktree add ../worktree-demo-1 -b feature/auth`

- List all worktrees

`git worktree list`

- Remove a worktree

`git worktree remove {{worktree_name}}`

- Prune non-existent worktrees (removed from disk)

`git worktree prune`


---

This is a test squash merge change.
