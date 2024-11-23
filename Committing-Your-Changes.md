### **Committing and Pushing Changes**

When you've finished making your changes and have tested them locally, it's time to commit your work:

---

**1. Stage Changes**

Use the following command to stage all changes:

```bash
git add .
```

This adds all modified and new files to the staging area, preparing them for the commit.

**2. Commit Changes**

Commit your changes with a meaningful commit message that describes the purpose of your changes:

```bash
git commit -m "Your commit message goes here"
```

A good commit message is concise and provides enough context about the changes made. Mifos follows its own commit style guidelines that you must follow. Learn more about it [here](https://github.com/openMF/mifos-mobile-cn/blob/master/COMMIT_STYLE.md).

**3. Push Changes**

Push your changes to your forked repository on GitHub:

```bash
git push origin new-branch-name
```
Replace `new-branch-name` with the name of the branch you created earlier.

This structure is easy to follow and provides clear instructions for committing and pushing changes to a project.
