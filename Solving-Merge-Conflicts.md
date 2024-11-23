### **Handling Merge Conflicts in a Pull Request**

In some cases, your pull request might encounter merge conflicts when the changes cannot be automatically merged with the main branch. To resolve merge conflicts:

1. **Update your local branch with the latest changes from the main repository:**

   ```bash
   git fetch upstream
   git checkout your-branch-name
   git rebase upstream/master
   ```

2. **Resolve Conflicts Manually:**

Git will pause when encountering conflicts. Open the affected files, resolve the conflicts manually, and save the changes.

3. **Stage Changes and Continue the Rebase:**

```bash
  git add .
  git rebase --continue
```

4. **Force Push the Changes:**
```bash
  git push --force origin your-branch-name
```
Your pull request will be updated with the resolved conflicts, and the reviewers can proceed with the review process.

> **Note:** Don’t forget to squash your commits to maintain a clean and concise commit history.  
> If you're unfamiliar with how to squash commits, refer to the [Squashing Your Commits Guide](https://github.com/openMF/mobile-wallet/wiki/Squashing-Your-Commits).
