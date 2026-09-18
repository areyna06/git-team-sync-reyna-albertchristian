# Team Sync Workflow

## 1. What did the rejected push error message tell you, and why did it happen?

The rejected push told me that the remote feature/loyalty-points branch had commits that my local branch did not have. Git rejected the push because it could not perform a fast-forward update.

This happened because another clone had already pushed changes to the shared branch while my current clone was still using an older version of the branch.

## 2. What's the actual difference between how you resolved Task 3 using merge and Task 4 using rebase?

In Task 3, I used merge. Git kept both lines of development and created a merge commit that combined the changes from Clone A and Clone B.

In Task 4, I used rebase. Git temporarily removed my local commit, updated the branch to the newest remote history, and then replayed my local commit on top of it.

The main difference is that merge preserves the branch history and creates a merge commit, while rebase rewrites the local commit history so the changes appear in a more linear sequence.

## 3. What one habit would have avoided both rejected pushes in this lab?

Fetching or pulling the latest version of the shared branch before starting new work would have avoided both rejected pushes.

For example, I could run:

git fetch origin

before making changes so I know whether another developer has already updated the remote branch.

## 4. Which approach, merge or rebase, would you default to on a shared team branch, and why?

I would normally use merge for work that has already been shared with other developers because merge does not rewrite existing shared commit history.

I would use rebase mainly for my own local commits that have not yet been pushed, because rebasing unpublished commits can keep the history cleaner without changing commits that other team members may already be using.