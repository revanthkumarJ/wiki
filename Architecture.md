This project is based on Clean Architecture.

<p align="center">
  <img src="https://github.com/user-attachments/assets/b4964d38-c04d-4711-9cfd-55c80782d7a2" alt="Clean Architecture 1" width="400">
  <img src="https://github.com/user-attachments/assets/ebba2eb3-bb50-4f85-8e87-30a2bc708c34" alt="Clean Architecture 2" width="400">
</p>


The presentation and UI layers are implemented in the app modules, while the data and domain layers are implemented in the core module. Each use case is a standalone feature of the wallet framework and can be directly used by the client apps.

The project is divided into a core library module and various application modules. Currently, the project has the following modules:

### core

This module is the core library module of the wallet framework. All the wallet-related use cases are present in this module.  
This module contains:  
1. The data and domain layers.  
2. All the Fineract API interaction is implemented in this module. Note that the wallet framework is extended on top of the self-service APIs in the Fineract backend.  
3. The data models are mapped by the use cases internally from the actual API models to simpler models that will be exposed to the client apps.  
4. All the API and data implementation is located [here](https://github.com/openMF/mobile-wallet/tree/master/core/src/main/java/org/mifos/mobilewallet/core/data).  
5. Models and use cases are located [here](https://github.com/openMF/mobile-wallet/tree/master/core/src/main/java/org/mifos/mobilewallet/core/domain).

### mifospay-shared

This module contains shared logic, utilities, and common code that is used across different platforms. It serves as the backbone for the cross-platform implementation of the project.

### Platform-Specific Modules

The project has transitioned to **Kotlin Multiplatform (KMP)**, and individual modules like Android, iOS, Desktop, and Web have been integrated into the shared architecture. These platform-specific implementations are now part of the following consolidated modules:

1. **mifospay-android**: Android-specific implementation.
2. **mifospay-ios**: iOS-specific implementation.
3. **mifospay-desktop**: Desktop-specific implementation.
4. **mifospay-web**: Web-based implementation.

