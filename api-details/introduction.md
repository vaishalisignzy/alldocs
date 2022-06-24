# Introduction

Onboarding Engine allows a flexible SDK solution for all onboarding platforms - entity or individual. It's data structure is designed to be infallible in all use cases of Signzy's onboarding solution. The design allows a user to custom-use the product in a way that suits their needs.

### Data Structure <a href="#data-structure" id="data-structure"></a>

**Merchant: represents an Entity (could be an organisation or an individual)**

**Tag: the molecular parts of the Entity / Individual (example: An Entity type merchant can have different tags for the company and directors)**

**Document: Any type of proof for that being**

You can create multiple merchants. Merchants can create a limited number of tags specified by Signzy. All documents are stored within the tag. There is also a limit to the number of documents. Customers have grant based access
