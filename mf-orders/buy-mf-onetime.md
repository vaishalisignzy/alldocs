---
description: Facilitate lumpsum investments for your investor
---

# Buy MF - Onetime

{% hint style="info" %}
**Ensure the following before placing a purchase order**

> 1. Your investor is [kyc compliant](https://docs.fintechprimitives.com/identity/overview)
> 2. You have an [investment account created](https://docs.fintechprimitives.com/mf-transactions/overview) for your investor
{% endhint %}

Once you have the investor and investment account created, follow the below steps to place a purchase order.

1. Create a purchase order
2. Make payment
3. Check the order state

**1. Create a purchase order**

Some funds are not allowed for purchases and some might temporarily stop accepting purchase orders. Make sure you check the `purchase_allowed` field is `true` for the fund scheme(s) you are placing the order for, using the Get fund scheme.

FP uses `MF Purchase` object to represent all the mutual fund purchase orders. You need to create a `MF Purchase` as a first step for placing a one time purchase order.

Call the Create mf purchase with the following json. Use the investment account of the investor for whom you are placing the order for.

```
{
  "mf_investment_account": "mfia_367a75826694614a539c0f82b196027",
  "scheme": "INF173K01FE6",
  "amount": 10000
}
```

A MF Purchase gets created for which you need to make a payment. Keep a note of the object `id` and `old_id`; you'll need these for making payments and checking the status of the order later on.

```
# Displaying only a part of the object for brevity
{
  "object": "mf_purchase",
  "id": "mfp_177177219f634373b01072986d2eea7d",
  "old_id": 9123,
  "mf_investment_account": "mfia_367a75826694614a539c0f82b196027",
  "amount": 10000
}
```

**2. Make payment**

You can use FP Payment APIs or work with payment providers directly to faciliate a payment for the order.

1.  You are using FP payment APIs

    To make a payment using internet banking or upi, make a request to Create payment with the following json. Use the order's `old_id` from the previous step. Use the `id` of the bank account belonging to the investor, with which you want him to make the payment.

    ```
    {
      "amc_order_ids": [9123],
      "bank_account_id": 23
    }
    ```

    Look for `token_url` in the response and redirect your investor to it to complete his payment. After your investor finishes the payment, FP redirects him to the postback URL configured on your account or to the `payment_postback_url` provided in the request. You'll receive `success` or `failure` in the `status` param. As a good security practice, do not completely rely on the `status` received in the postback call. Instead check the status of the payment from your server before giving a final confirmation to your investor.\
    Learn more about payment states.


2.  You are using FPDocs payment providers directly



    After you have collected the money from your investor, confirm the purchase order by calling the Update mf purchase with the following json:

    ```
    {
      "id": "mfp_177177219f634373b01072986d2eea7d",
      "state": "confirmed"
    }
    ```

    After the money is settled into the scheme's bank account, call the Create mf settlement detail to give us the settlement details so we can reconcile the order with the money received. You need to send the following details about the settlement:

    ```
    {
      "mf_purchase": "mfp_177177219f634373b01072986d2eea7d",
      "payment_type": "netbanking",
      "utr_no": "889121212",
      "bank_account_no": "18603051137433",
      "beneficiary_account_no": "1143005051340",
      "beneficiary_account_title": "AMC Mutual Fund Pool AC",
      "settlement_processed_at": "2020-04-09T12:00:09"
    }
    ```



**3. Track the order**

Call the fetch mf purchase to check the `state` of the order.\
When the payment is successful, the order state becomes `confirmed`.&#x20;



#### Order Processing <a href="#order-processing" id="order-processing"></a>

Orders in `confirmed` state will be sent for processing and the object state will move to `submitted`. After the order is processed successfully (typically takes one day) - units are allotted and the object state will move to `successful`.\
For a successful order, review the following key attributes of the `mf_purchase` object:\
`allotted_units`: the number of units issued for the purchase amount\
`purchased_price`: the price per unit at which the units are issued\
`folio_number`: the folio (aka mutual fund account) in which the units are issued. You'll need this to place additional purchases and redemption orders

#### Testing <a href="#testing" id="testing"></a>

In sandbox, use the simulation API to simulate `successful` and `failed` orders to help you during the integration process. Use the following json to simulate the order to `successful` state.

```
{
  "status": "SUCCESSFUL"
}
```

A testing folio number is issued during simulation, which you can use to place additional purchase orders or redemption orders.

