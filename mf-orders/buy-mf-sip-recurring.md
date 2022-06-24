---
description: Facilitate SIP investments for your investor
---

# Buy MF - SIP (Recurring)

Not all schemes allow for SIP investments. Make sure you check the `sip_allowed` field is `true` for the scheme you are creating an sip plan for, using the Get fund scheme API.

**1. Create a SIP plan**

Call the create sip API with the following json. Use the `id` of the payment mandate through which the money will be debited from the investor's bank account on every installment.

```
{
  "orders": [
    {
      "isin": "INF204KA1B64",
      "amount": 10000,
      "start_day": "2",
      "frequency": "MONTHLY",
      "installments": 20,
      "mandate_id": 23
    }
  ]
}
```

On every installment, FP does the following automatically:

1. Creates a purchase order
2. Debits the money from the investor's bank account
3. Submits the purchase order for processing

_Note: Currently the payments for the SIP investments have to be processed using FP Payment APIs (via nach only). Ability to use your own FPDocs payment providers is under implementation and will be available soon_

**2. Fetch the installments**

Fetch the installments of the SIP plan using the fetch installments API.

**3. Track the SIP installment**

FP uses `MF Purchase` object to represent the sip installment.

Check the status of an installment using the fetch a mf purchase API. Use the `id` of the installment from the previous step.

#### Testing <a href="#testing" id="testing"></a>

In the sandbox, use the sip simulation API to trigger generation of future sip installments. After generating the installments, use the order simulation API to test various success and failure scenarios of the installments.
