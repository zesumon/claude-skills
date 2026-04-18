# Sync Branch

Keep your branch up to date with the main branch.

## Usage

```
/git/sync
```

## What it does

1. Fetches latest changes from origin
2. Rebases current branch on top of main (or master)
3. Handles common conflicts by prompting you

## Steps

```bash
# Fetch latest from remote
git fetch origin

# Detect default branch
DEFAULT_BRANCH=$(git remote show origin | grep 'HEAD branch' | awk '{print $NF}')

# Rebase on default branch
git rebase origin/$DEFAULT_BRANCH
```

If there are conflicts, list them and ask the user how to proceed.

After a successful sync, show a summary of how many commits were rebased and if the branch is now up to date.