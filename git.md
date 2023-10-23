# GIT
## Stashing changes
### Stash w/ a message
```bash
git stash push -m "my_stash_name"
git stash apply stash^{/my_stash_name}
```

### Stash w/o a message
```bash
git stash
git stash apply # pop & apply latest stash
git stash apply stash@{n} # pop nth stash and apply it
```

### List stashes
```bash
git stash list
```
