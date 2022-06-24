---
description: Facilitate redemptions for your investor
---

# Sell MF

Mutual fund units are associated with folios. You can treat folios as sub-accounts under the investment account. You can fetch the list of folios for an investment a/c from the holdings report API. `redeemable_units` shows the number of units that are available for selling. You can use the Signzy APIs to sell the units partially or in total.

**1. Create a sell order**

Call the create mf redemption API with the following json. Use the investment account of the investor for whom you are placing the order for. Pass the `folio_number` and `scheme` from which you are selling the units.

```
{
  "mf_investment_account": "mfia_189111b00566431db0dace5332db519c",
  "folio_number": "15075102",
  "amount": 10000,
  "scheme": "INF173K01FQ0"
}
```

A MF Redemption gets created in `pending` state. Keep a note of the object id for tracking the status of the order.

```
# Displaying only a part of the object for brevity
{
  "object": "mf_redemption",
  "id": "mfr_15f8d86bae614801bab5accaed131abc",
  "old_id": 6597,
  "mf_investment_account": "mfia_189111b00566431db0dace5332db519c",
}
```

**2. Confirm the order**

Call the update mf redemption API to confirm the order. Signzy sends it for processing only after confirmation. Use the following json:

```
{
  "id": "mfr_15f8d86bae614801bab5accaed131abc",
  "state": "confirmed"
}
```

**2. Track the order**

Call the fetch mf redemption API to check the `state` of the sell order.\
When the order is successfully submitted to the AMC, the order status becomes `SUBMITTED`. Learn more about the order states

Orders in `confirmed` state will be sent for processing and the object state will move to `submitted`. After the order is processed successfuly and units are repurchased by the AMC, the object state will move to `successful`; the redeemed units, amount and the price is available in `redeemed_units`, `redeemed_amount` and `redeemed_price` attributes of the mf redemption object.

#### Testing <a href="#testing" id="testing"></a>

In sandbox environment, you can use the simulation API to simulate `successful` and `failed` orders to help you during the integration process. Use the following json to simulate the order to `successful` state.

```
{
  "status": "SUCCESSFUL"
}
```
