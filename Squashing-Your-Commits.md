It is common for pull requests to undergo multiple rounds of review before being merged. To keep the Git history clean and organized, you should always squash your commits before finalizing the merge. Here's how you can do it:

1. Squash your commits:

   `git rebase -i HEAD~x`

Replace **x** with the number of commits you want to squash. An interactive rebase will open, allowing you to choose how to combine the commits. Change **pick** to **squash** (or simply **s**) for all but the topmost commit. Save and exit the editor.

2. Amend the commit message if needed.

   `git commit --amend`

3. Force push the changes to your forked repository:

   `git push --force origin your-branch-name`

Please note that force pushing rewrites the Git history, so use it with caution.