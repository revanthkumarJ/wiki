### **Committing and Pushing Changes**

When you've finished making your changes and have tested them locally, it's time to commit your work:

---

## **1. Stage Changes**

Use the following command to stage all changes:

```bash
git add .
```

This adds all modified and new files to the staging area, preparing them for the commit.

## **2. Commit Changes**

Commit your changes with a meaningful commit message that describes the purpose of your changes:

```bash
git commit -m "Your commit message goes here"
```

A good commit message is concise and provides enough context about the changes made. Mifos follows its own commit style guidelines that you must follow. Learn more about it [here](https://github.com/openMF/mifos-mobile-cn/blob/master/COMMIT_STYLE.md).

## **3. Push Changes**

Push your changes to your forked repository on GitHub:

```bash
git push origin new-branch-name
```
Replace `new-branch-name` with the name of the branch you created earlier.


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

4. **Check Detekt Errors**
   
   Run this command to check for Detekt errors:
```bash
./gradlew detekt
```
5. **Run Lint and Test Commands**

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

This structure is easy to follow and provides clear instructions for committing and pushing changes to a project.
