# Project Overview

This project is based on **Clean Architecture** and follows **Modularization** principles to ensure scalability, maintainability, and easy collaboration among developers.

## The Use of Clean Architecture

- **Clarity**: The architecture is easy for developers to understand and follow, ensuring that the system remains maintainable and extensible.
- **Collaboration**: It supports multiple developers working on the same codebase, with clear separation of concerns and independent modules.
- **Build Efficiency**: The design minimizes build times, improving overall productivity.

<table style="width: 100%; table-layout: fixed; border-collapse: collapse;">
  <thead>
    <tr>
      <th colspan="3" align="center" style="text-align: center; font-size: 1.5em; padding: 10px;">Clean Architecture</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center" style="padding: 10px;">
        <img src="https://github.com/user-attachments/assets/5ded3799-0746-4b67-816c-cb149b150c5b" alt="Image 2" style="width: 100%; max-width: 200px;"/>
      </td>
      <td align="center" style="padding: 10px;">
        <img src="https://github.com/user-attachments/assets/79f66eb7-e664-43e7-963c-d8e5610c3c25" alt="Image 1" style="width: 100%; max-width: 200px;"/>
      </td>
      <td align="center" style="padding: 10px;">
        <img src="https://github.com/user-attachments/assets/6a949e74-73bd-4506-be1b-8a500fc93b00" alt="Image 3" style="width: 100%; max-width: 200px;"/>
      </td>
    </tr>
  </tbody>
</table>

## **Modularization**

- The project is divided into independent, self-contained modules, each with its own `build.gradle` file and `src` folder.
- This structure allows for independent development, testing, and maintainability of each feature.
- The modular approach promotes separation of concerns, making it easier to manage and extend the project.

## Project Modules Overview

### 1. **core**
The core module is the central library of the wallet framework, containing the foundational components and business logic.
   - Includes the data and domain layers.
   - Implements interactions with the Fineract API.
   - Maps and simplifies data models to be exposed to client apps.
   - All the API and data implementation is located [here](https://github.com/openMF/mobile-wallet/tree/master/core/src/main/java/org/mifos/mobilewallet/core/data).
   - Models and use cases are located [here](https://github.com/openMF/mobile-wallet/tree/master/core/src/main/java/org/mifos/mobilewallet/core/domain).

### 2. **mifospay-shared**
This module contains shared logic, utilities, and common code for the cross-platform implementation of the project.

### 3. **Platform-Specific Modules**
These modules are designed to cater to platform-specific needs while maintaining a shared architecture:
   - **mifospay-android**: Android-specific implementation.
   - **mifospay-ios**: iOS-specific implementation.
   - **mifospay-desktop**: Desktop-specific implementation.
   - **mifospay-web**: Web-based implementation.

### 4. **feature**
The feature module contains independent, feature-specific implementations, each encapsulated in its own folder and submodules. This modularized approach allows for isolated development and testing. Example features include:
   - **payments**: Handles payment processing and transactions.
   - **settings**: Manages user configuration and settings.
   - **notifications**: Handles push notifications and alerts.

Each feature is designed to be self-contained, promoting modular development and ease of updates.
