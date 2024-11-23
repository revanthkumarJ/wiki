This project is based on [Clean Architecture](https://github.com/android10/Android-CleanArchitecture).  

The presentation and ui layers are implemented in the app modules while the data and domain layers are implemented in the core module. Each use case is a standalone feature of the wallet framework and can be directly used by the client apps. 

The project is divided into a core library module and other application modules. Currently, the project has 3 modules -
### core

This module is the core library module of the wallet framework. All the wallet related use cases are present in this module.   
This module contains -   
1. The data and domain layers  
2. All the fineract api interaction is implemented in this module. Note that the wallet framework is 
   extended on top of the self service apis in the fineract backend  
3. The data models are mapped by the use cases internally from the actual api models to simpler models 
   that will be exposed to the client apps    
4. All the api and data implementation is located [here](https://github.com/openMF/mobile-wallet/tree/master/core/src/main/java/org/mifos/mobilewallet/core/data)   
5. Models and use cases are located [here](https://github.com/openMF/mobile-wallet/tree/master/core/src/main/java/org/mifos/mobilewallet/core/domain)  

### mifospay

mifospay module is both merchant and consumer facing wallet app and a reference implementation of the use cases available 
in the core library module. In addition to that, there are some use cases which are based on UPI SDK. 
Currently, UPI use cases are not functional because of non-availability of UPI SDK. 


### app (PixiePay)

app module contains the PixiePay app which is an India specific merchant wallet and payment collection app based on top of UPI and other payment settlement capabilities like Aadhar Pay and payment gateways.
This module has its own data layer that interacts with RBL Bank for actual banking APIs alongside the Fineract backend from the core library module.

Note: The module `app` (PixiePay) has been moved to another repository.