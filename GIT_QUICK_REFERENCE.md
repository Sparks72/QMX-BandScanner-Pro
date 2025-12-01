# Git Quick Reference Card

## Essential Commands

### Initial Setup
```bash
git config --global user.name "Paul Mitchell"
git config --global user.email "your.email@example.com"
git init                           # Initialize new repository
```

### Daily Workflow
```bash
git status                         # Check what's changed
git add filename.html              # Stage specific file
git add .                          # Stage all changes
git commit -m "message"            # Commit with message
git push                           # Upload to remote
git pull                           # Download from remote
```

### Branching
```bash
git branch                         # List branches
git branch feature-name            # Create branch
git checkout feature-name          # Switch to branch
git checkout -b feature-name       # Create and switch
git merge feature-name             # Merge branch into current
git branch -d feature-name         # Delete branch
```

### History and Info
```bash
git log                            # View commit history
git log --oneline                  # Compact history
git log --graph --oneline          # Visual history
git diff                           # Show unstaged changes
git diff --staged                  # Show staged changes
git show commit-hash               # Show specific commit
```

### Undoing Changes
```bash
git checkout -- filename           # Discard file changes
git reset HEAD filename            # Unstage file
git reset --soft HEAD~1            # Undo last commit (keep changes)
git reset --hard HEAD~1            # Undo last commit (discard changes)
git revert commit-hash             # Create new commit that undoes
```

### Remote Repositories
```bash
git remote add origin url          # Add remote
git remote -v                      # List remotes
git push -u origin main            # First push to main
git push origin branch-name        # Push specific branch
git clone url                      # Copy remote repository
```

### Tags (Versioning)
```bash
git tag                            # List tags
git tag v1.0.0                     # Create lightweight tag
git tag -a v1.0.0 -m "message"     # Create annotated tag
git push origin v1.0.0             # Push specific tag
git push origin --tags             # Push all tags
git tag -d v1.0.0                  # Delete local tag
git push origin :refs/tags/v1.0.0  # Delete remote tag
```

### Stashing (Temporary Storage)
```bash
git stash                          # Save changes temporarily
git stash list                     # List stashed changes
git stash apply                    # Restore stashed changes
git stash pop                      # Restore and remove from stash
git stash drop                     # Delete stashed changes
```

### Inspection
```bash
git blame filename                 # See who changed what
git show commit-hash:filename      # View file at commit
git ls-files                       # List tracked files
```

## Common Scenarios

### Scenario 1: Made Changes, Want to Commit
```bash
git status                         # See what changed
git add .                          # Stage all changes
git commit -m "Added frequency memory feature"
git push
```

### Scenario 2: Want to Try Something Experimental
```bash
git checkout -b experiment         # Create experimental branch
# Make changes...
git add .
git commit -m "Testing new scan algorithm"
# If good:
git checkout main
git merge experiment
git branch -d experiment
# If bad:
git checkout main
git branch -D experiment           # Force delete
```

### Scenario 3: Messed Up, Want to Start Over
```bash
git status                         # See what's wrong
git checkout -- .                  # Discard all changes
# OR
git reset --hard HEAD              # Reset to last commit
```

### Scenario 4: Want to See Old Version
```bash
git log --oneline                  # Find commit hash
git checkout commit-hash           # View that version
# Look around...
git checkout main                  # Return to current
```

### Scenario 5: Create New Release
```bash
# Update version in code
# Update CHANGELOG.md
git add .
git commit -m "Version 1.1.0: Added 4m band support"
git tag -a v1.1.0 -m "Release 1.1.0"
git push origin main
git push origin v1.1.0
# Then create release on GitHub
```

### Scenario 6: Someone Contributed, Want to Merge
```bash
git fetch origin                   # Get latest changes
git checkout main
git merge origin/contributor-branch
git push
```

## Best Practices

1. **Commit messages should be clear**:
   - Good: "Fix: Correct S-meter conversion for weak signals"
   - Bad: "fixed bug"

2. **Commit often, push regularly**
   - Small commits are easier to understand
   - Regular pushes protect against data loss

3. **Use branches for features**
   - Keep main branch stable
   - Experiment on feature branches

4. **Tag releases**
   - Makes it easy to find specific versions
   - Enables rollback if needed

5. **Update documentation**
   - Keep README.md current
   - Update CHANGELOG.md for each version

6. **Review before committing**
   - Use `git diff` to see changes
   - Make sure you're not committing debug code

## Emergency Commands

### "I committed to wrong branch!"
```bash
git log --oneline -1              # Get commit hash
git reset --hard HEAD~1           # Remove from current branch
git checkout correct-branch
git cherry-pick commit-hash       # Apply to correct branch
```

### "I need to undo a pushed commit!"
```bash
git revert commit-hash            # Creates new commit that undoes
git push
```

### "Everything is broken!"
```bash
git status                        # Assess damage
git stash                         # Save any work
git reset --hard origin/main      # Reset to remote version
```

## Useful Aliases (Add to ~/.gitconfig)

```ini
[alias]
    st = status
    co = checkout
    br = branch
    ci = commit
    unstage = reset HEAD --
    last = log -1 HEAD
    visual = log --graph --oneline --all
    amend = commit --amend
```

Then use: `git st` instead of `git status`, etc.

---

**Need more help?**
- Official Git docs: https://git-scm.com/doc
- Interactive tutorial: https://learngitbranching.js.org/
- Git cheat sheet: https://education.github.com/git-cheat-sheet-education.pdf

**73!**  
Paul Mitchell - VK2AAQ
