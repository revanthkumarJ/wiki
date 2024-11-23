We have the following branches :

* **dev**

All the contributions should be pushed to this branch. If you're making a contribution, you are supposed to make a pull request to dev. Please make sure it passes a build check on Travis.

  It is advisable to clone only the development branch using the following command:

  `git clone -b <branch> <remote_repo>`

  With Git 1.7.10 and later, add --single-branch to prevent fetching of all branches. Example, with development branch:

  `git clone -b dev --single-branch https://github.com/username/mobile-wallet.git`* * * > 

* **master**

The master branch contains all the stable and bug-free working code. The development branch once complete will be merged with this branch.