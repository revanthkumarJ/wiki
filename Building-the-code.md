# **Steps to Clone and Set Up the Mobile Wallet Project**

1. **Clone the Repository**
   - Using HTTP:  
     ```bash
     git clone https://github.com/openMF/mobile-wallet.git
     ```

2. **Open Android Studio**  
   - Launch Android Studio on your system.

3. **Import the Project**  
   - Click on **`Open an existing Android Studio project`**.  
   - Browse to the directory where you cloned the `mobile-wallet` repository.  
   - Select the folder and click **OK**.  

4. **Gradle Sync**  
   - Let Android Studio import the project.  
   - You may encounter an error during the Gradle build related to missing properties:  
     - **`RblClientIdProp`**  
     - **`RblClientSecretProp`**  

5. **Add Environment Variables**  
   - Define the following environment variables with any value:  
     - `RblClientIdProp`  
     - `RblClientSecretProp`  

     Example for Linux/Mac:  
     ```bash
     export RblClientIdProp=your_value
     export RblClientSecretProp=your_value
     ```

     Example for Windows (Command Prompt):  
     ```cmd
     set RblClientIdProp=your_value
     set RblClientSecretProp=your_value
     ```

6. **Sync the Project Again**  
   - In Android Studio, click **File > Sync Project with Gradle Files**.  
   - Wait for the sync to complete successfully.  

You are now ready to start working on the `mobile-wallet` project!
