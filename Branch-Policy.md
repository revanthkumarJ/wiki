We have the following branches :
- dev
- master

### **dev**

- All contributions should be pushed to the `dev` branch.
- When making a contribution, you are supposed to make a **Pull Request** (PR) to the `dev` branch.
- Please make sure it passes a build check on **Travis** before submitting the PR.

#### Cloning the Development Branch

It is advisable to clone only the development branch using the following command:

```bash
git clone -b <branch> <remote_repo>
```
With Git 1.7.10 and later, add --single-branch to prevent fetching of all branches. Example, with development branch:

```bash

  `git clone -b dev --single-branch https://github.com/username/mobile-wallet.git`* * * >
```


### **master**

The master branch contains all the stable and bug-free working code. The development branch once complete will be merged with this branch.
