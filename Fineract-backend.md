The wallet framework uses Fineract backend at its core to manage users, wallet accounts and funds transfer.

Almost all of the use cases are based on top of self service apis from the Fineract backend and limits the data scope to that of the self service user only.   
However, for some use cases, other apis are also used. 
For example, the [SearchClient](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/domain/usecase/SearchClient.java) use case is used to correctly identify the client using the VPA or the Mobile Number provided. This is done to make sure that the user knows where the wallet funds will be transferred. Since, self service api foes not allow a self service user to read clients of other users, this use case uses the search api from the Fineract with a user authorised to only be able to read all functions.  
(This user in the demo server is **username**: mifospayadmin, **password**: password1).   
This user has a predefined set of roles and permission so as to make sure that it isn't allowed to perform any write operations in the backend.

Some important points related to the use of Fineract backend -
* The Virtual Payment Address (VPA) of a user is the `externalId` of the client associated with the user  

* Each wallet account is created as a savings account in the Fineract backend. 
There are different`savingsProductId` for mechants and consumers in order to differentiate them. 
The `savingsProductId` for merchants and consumers needs to be defined in the core library module. 
(`MIFOS_MERCHANT_SAVINGS_PRODUCT_ID`, `MIFOS_CONSUMER_SAVINGS_PRODUCT_ID` in 
[Constants](https://github.com/openMF/mobile-wallet/blob/master/core/src/main/java/org/mifos/mobilewallet/core/utils/Constants.java))

* KYC Details, Invoice Details, Saved Cards and Notification record of a user are stored in the 
datatables `kyc_level1_details`, `invoices`, `saved_cards`, `notifications` respectively. 
These datatables are defined in the client associated with the user. 

* KYC Docs of a user are stored in the document field of the client associated with the user.

* Unique Receipt Link is of the following format: `https://receipt.mifospay.com/{receiptId}`

* Unique Payment Link is of the following format: `https://invoice.mifospay.com/{clientId}/{invoiceId}`

* Push Notifications: We are using Firebase data messages to push notifications to the users. 
Datatable for notifications is for user to keep record of the important notifications. 
This datatable will be managed at the server-side as notifications will be sent from the server to Firebase 
and then Firebase will send it to the users. Note: Server-side code has not been implemented yet.