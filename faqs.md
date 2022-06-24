# FAQ's

**What is Entity Id in "Onboard a customer" API?**

It is an unique number given by the business for the customers. Eg. Bank account number

**What is Kit Number in "Onboard a customer" API?**

Kit number is mapped to card number whereas card number should not be printed on clear

**What are all the fields that can be updated in the "Update customer details" API?**

All fields can be updated unless it is reflecting in KYC

**Can Entity Id be updated in the "Update customer detail" API?**

No, it cannot be updated

**Will the wallet balance will be double in case of two cards?**

Wallet balance will remain single and it can be used for both cards.

**Does KYC process required for adding a card?**

No, KYC is not required.

**Can multiple cards be fetched in the "View linked card" API?**

Yes, any number of cards linked to an entity Id can be fetched

**Using kit numbers can the card numbers be fetched?**

Yes, it can be done. \
\
**How is merchant data framed in Make QR payment API?**

Merchant data is framed based on tag length value. There is a separate format to be followed which will be shared based on the business model

**We don't store the card number, then how can the card number field be sent?**

Retrieve the card number using the API and the card number need to be sent in the cardNo field.\
\
**Can the Blocked card be unblocked in Lock/Unlock Card API?**

Block option is a permanent block. It cannot be unlocked, it can only be replaced

**Is it possible to Replace the card when the card is locked?**

No, only when the card is blocked it can be replaced

**What is externalTransactionId in the "View txn status by External ID" API?**

It is a unique id generated for each and every transaction by the party calling the API

**What is transactionType in the "Debit Customer Account" API?**

It is an enum value that needs to be provided at the time of request as the Signzy system requires.

**What's productId?**

It is a type of wallet

**How to replaceCard?**

Using block card API, once the card is blocked, the card can be replaced.\
\
**Can balance be fetched using a card number?**

No, only with entity Id.\
\
**Is it is possible to convert n number to physical cards?**

Yes, we can.

**Did the card delivered directly to the customer's registered contact address?**

Yes, it will be delivered directly to the customer's registered contact.



