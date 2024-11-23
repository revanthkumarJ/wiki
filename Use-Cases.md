Each use case in the core module is a standalone feature of the wallet framework.

Each use case has a set of request values that can be passed to the use case execution and a set of 
response value that the client can get back after the execution is completed. These use cases should 
be executed from the presenters in the client app by using 
[UseCaseHandler](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/base/UseCaseHandler.java)

Currently, the following use cases are available - 

* [AuthenticateUser](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/user/AuthenticateUser.java) - Authentication using the self service apis.     
_RequestValues_ - username, password  
_ResponseValues_ - The authenticated user  

* [FetchAccount](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/account/FetchAccount.java) - Fetches the wallet account for the client using the wallet savingsProductId defined in the core module.   
_RequestValues_ - clientId
_ResponseValues_ - The wallet account associated with the client  

* [FetchAccounts](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/account/FetchAccounts.java) - Fetches all the savings account for the client   
_RequestValues_ - clientId   
_ResponseValues_ - List of accounts  

* [SearchClient](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/client/SearchClient.java) - Finds the client using the vpa/mobileNo provided   
_RequestValues_ - vpa/externalId of the client   
_ResponseValues_ - List of search results

* [TransferFunds](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/account/TransferFunds.java) - Makes a funds transfer between the two wallet accounts using third party transfer from self service apis.    
_RequestValues_ - fromClientId, toClientId, amount

* [FetchAccountTransactions](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/account/FetchAccountTransactions.java) - Fetches the recent transactions for the account  
_RequestValues_ - accountId  
_ResponseValues_ - List of transactions

* [FetchClientData](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/client/FetchClientData.java) - Fetches the details of a client  
_RequestValues_ - clientId (optional)   
_ResponseValues_ - Client details

* [RegisterUser](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/user/RegisterUser.java) - Creates a new user in the fineract backend: creates a new self service user, creates a new client and creates a new wallet account.  
_RequestValues_ - RegisterPayload 

* [BlockUnblockCommand](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/account/BlockUnblockCommand.java) - Blocks or Unblocks an account of a client  
_RequestValues_ - accountId, command (Block/Unblock)

* [FetchMerchants](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/account/FetchMerchants.java) - Fetches all the registered merchants  
_RequestValues_ - None
_ResponseValues_ - List of merchants

* [FetchAccountTransfer](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/account/FetchAccountTransfer.java) - Fetches transfer details of a specific transaction  
_RequestValues_ - transferId
_ResponseValues_ - Transfer Details

* [FetchTransactionReceipt](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/account/FetchTransactionReceipt.java) - Fetches receipt of a transaction   
_RequestValues_ - transactionId
_ResponseValues_ - Receipt PDF

* [FetchClientImage](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/client/FetchClientImage.java) - Fetches client's image   
_RequestValues_ - clientId
_ResponseValues_ - Image decoded in Base64

* [UpdateClient](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/client/UpdateClient.java) - Updates mobileNo or any other field of a client
_RequestValues_ - clientEntity containing the fields one wants to update (example: mobileNo), clientId

* [FetchClientImage](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/client/FetchClientImage.java) - Fetches client's image  
_RequestValues_ - clientId
_ResponseValues_ - Image decoded in Base64

* [FetchInvoice](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/invoice/FetchInvoice.java) - Fetches a specific invoice of a client
_RequestValues_ - uniquePaymentLink
_ResponseValues_ - Invoice

* [FetchInvoices](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/invoice/FetchInvoices.java) - Fetches all the invoices of a client  
_RequestValues_ - clientId
_ResponseValues_ - List of invoices

* [FetchKYCLevel1Details](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/kyc/FetchKYCLevel1Details.java) - Fetches KYC level 1 details of a client
_RequestValues_ - clientId
_ResponseValues_ - KYC Level 1 details

* [UpdatesKYCLevel1Details](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/kyc/UpdatesKYCLevel1Details.java) - Updates KYC level 1 details of a client  
_RequestValues_ - clientId

* [UploadKYCDocs](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/kyc/UploadKYCDocs.java) - Uploads KYC documents of a client  
_RequestValues_ - entityType, clientId, docname, identityType, file

* [UploadKYCLevel1Details](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/kyc/UploadKYCLevel1Details.java) - Upload KYC level 1 details of a client
_RequestValues_ - clientId, KYC level 1 details

* [FetchNotifications](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/notification/FetchNotifications.java) - fetches all the notifications of a client
_RequestValues_ - clientId
_ResponseValues_ - List of notifications

* [AddCard](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/savedcards/AddCard.java) - Adds a new credit card
_RequestValues_ - clientId, card details

* [DeleteCard](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/savedcards/DeleteCard.java) - Deletes a credit card of a client
_RequestValues_ - clientId, cardID

* [EditCard](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/savedcards/EditCard.java) - Updates a credit card of a client
_RequestValues_ - clientId, new card details

* [FetchSavedCards](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/savedcards/FetchSavedCards.java) - Fetches saved credit cards of a client
_RequestValues_ - clientId
_ResponseValues_ - List of cards

* [RequestOTP](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/twofactor/RequestOTP.java) - Sends an OTP on client's registered mobile number or email Id
_RequestValues_ - deliveryMethod

* [ValidateOTP](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/twofactor/ValidateOTP.java) - Validates an OTP token  
_RequestValues_ - token
_ResponseValues_ - accessToken

* [UpdateUser](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/user/UpdateUser.java) - Updates email Id or any other field of a user  
_RequestValues_ - userEntity containing the fields one wants to update (example: email), clientId
