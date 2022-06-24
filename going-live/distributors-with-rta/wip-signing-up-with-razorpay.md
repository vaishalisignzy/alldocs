---
description: >-
  Learn how to signup and configure your Razorpay account to process payments
  for mf investments
---

# WIP - Signing up with Razorpay



**Action items**

* You need to create two separate razorpay accounts and sign up for Razorpay Payments (to collect money from investors) and Razorpay Route (to transfer money to the AMCs) in each of those accounts
* Ensure the following (in each of your razorpay accounts):
  * Fee Credits are enabled [Read More](https://razorpay.com/docs/payments/dashboard/my-account/credits/#fee-credits)
  * Route settlement time is less than T+1 days
  * `signzy.com` domain is whitelisted
  * Create a letter in your company's letterhead and request Razorpay to whitelist the domain `signzy.com`. Get this letter signed by the authorized signatory(ex: Your company's CEO) and include your company's official seal as well. Send the scanned copy of this image via email to Razorpay to whitelist the said domain. This is required to ensure that the payments can be initiated from this domain. Please refer this [sample form](https://docs.fintechprimitives.com/going-live/Razorpay\_Domain\_Whitelisting\_Request\_Form.pdf) for more details

{% hint style="info" %}
We've seen delays/rejections in your Razorpay Account Activation if your corporate website isn't reflecting your mutual business properly. At the minimum, make sure your website talks about the mutual fund business, pricing, your company address, terms and conditions and privacy policies. Your Razorpay RM can help with more specific details and fast track your account activation.
{% endhint %}

**Razorpay FAQs**

_Why do we require two accounts?_\
In order to reduce the risks like cybercrimes, money laundering etc, SEBI has mandated that all payments must be made by investors exclusively from the pre-registered bank accounts. To ensure this, you need Third Party Validation(TPV). One Razorpay account must have Third Party Validation enabled so that we can enable TPV transactions via Netbanking and UPI mode. The other account is required for managing E-Mandates.
