# **Getting Started with Mobile Wallet (Mifos Pay)**

Before you begin, ensure you have already downloaded and correctly set up the Android Studio SDK. You can find a guide on how to do this here: [Setting up Android Studio](http://developer.android.com/sdk/installing/index.html?pkg=studio).

---

## **1. Fork the Git Repository**

Forking the repository is the first step to start contributing. Click on the **"Fork"** button in the top-right corner of the [Mobile Wallet (Mifos Pay) repository](https://github.com/openMF/mobile-wallet) to create your own fork.

![Fork Button](https://user-images.githubusercontent.com/44428198/254533248-3016c6eb-30b7-492b-91e8-dbbb61f76775.png)

Forking creates a copy of the project under your GitHub account. This enables you to work on changes without affecting the original repository directly.

---

## **2. Clone the Forked Repository**

Once you have forked the repository, you need to clone it to your local development environment. Open a terminal or Git Bash and use the following command:

```bash
git clone https://github.com/yourUsername/mobile-wallet.git
```

Replace **yourUsername** with your actual GitHub username. Cloning creates a local copy of the repository on your machine, allowing you to make changes and contributions.



## **3. Working Locally on Your Cloned Repository**

After cloning, navigate to the project directory using the terminal or Git Bash.

Before making any changes, create a new branch dedicated to the feature or bug fix you'll be working on:

``` bash
git checkout -b "new-branch-name"
```

Ensure that **new-branch-name** reflects the purpose of your changes (e.g., **add-payment-feature** or **fix-bug-123**).

Make the necessary changes to the files to address the issue you're working on. Once you're done, you will be ready to proceed with verifying and committing your changes.

## **4. Perform a Gradle Check**

All your pull requests must pass the CI build only then, it will be allowed to merge. Sometimes, when the build doesn't pass you can use these commands in your local terminal and check for the errors.

- **We've commited to use Material3 design in our project. And added lint check for not to use any M2 libraries in our project.**
- **And when adding new library, please make sure to follow the naming convention and place in sequential order(A->Z).**

In MacOS, Windows or Linux, you should run the following commands before opening a PR, and make sure to pass all the commands:

**In order to enhance our development process, we have implemented Git hooks in our project. To install these hooks locally, simply run the command ./gradlew installGitHooks. This will ensure that the Git hooks are installed on your local machine.**

### **Commands to Run**
1. **Check Build Logic**  
   Run the following command to verify that the build logic is configured correctly:  
```bash
./gradlew check -p build-logic
```

2. **Apply Spotless Formatting**
  Check and apply formatting to any file with this command:
```bash
./gradlew spotlessApply --no-configuration-cache
```
3. **Generate Dependency-Guard Baseline** 
   Use this command to generate a dependency-guard baseline:
```bash
./gradlew dependencyGuardBaseline
```

4.** Check Detekt Errors**
Run this command to check for Detekt errors:
```bash
./gradlew detekt
```
5.**Run Lint and Test Commands**
Execute this command to check for lint and test errors:
```bash
./gradlew testDemoDebug :lint:test :mifospay:lintProdRelease :lint:lint
```

6. **Build the Project**
Build the project using the following command:
```bash
./gradlew build
```

7. **Update Prod Release Badging**
   Update the project badging with this command:
```bash
./gradlew updateProdReleaseBadging
```

### **Alternative**

Run the `ci-prebuild.sh` (for Linux/macOS) or `ci-prebuild.bat` (for Windows) script to execute all the above commands in one go.
