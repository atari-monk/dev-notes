## Rebase

Batch Rename Commit Messages with VS Code

### Quick Setup

```bash
git config --global core.editor "code --wait"
```

This lets Git use VS Code for rebase editing instead of vim.

### The Process

1. **Start rebase from first commit**
   ```bash
   git rebase -i --root
   ```

2. **Mark commits to change**  
   In VS Code: change `pick` → `reword` on target commits. Save & close tab.

3. **Edit each message**  
   VS Code opens for each commit. Edit message (e.g., `post` → `note`). Save & close.

4. **Push rewritten history**
   ```bash
   git push origin main --force
   ```

### Key Points

- `reword` stops at each commit, lets you edit message, then continues
- Save + close VS Code tab after each edit to proceed
- Use `--force-with-lease` instead of `--force` on shared branches
- All commit SHAs change after rebase