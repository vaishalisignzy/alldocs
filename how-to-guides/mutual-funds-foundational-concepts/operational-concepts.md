# Operational Concepts

## Transaction Cycle

The operating cycle of a mutual fund can be summarized as below:

* Investor transaction is accepted by AMC
* Transaction is intimated to RTA back office
* NAV is applied to the transaction
* Units are added (purchase) or reduced (redemption) in the folio of investors
* Inflow and outflow resulting from transactions is reported to the AMC Treasury
* Units issued and redeemed for the day are consolidated
* Unit capital is updated for increase/decrease from the transactions
* Unit capital is communicated to AMC fund accounts
* Portfolio is valued by fund accounts/custodian
* NAV computation is done using the portfolio value and updated unit capital
* NAV is communicated to RTA for applying to investor transactions

💡 The AMC (or its custodian) computes the NAV at the end of the day, after the markets have closed.

## NAV Calculation

NAV is calculated as:

> (Market value of the portfolio - Expenses and liabilities) / (Number of units outstanding)

The number in the denominator can be provided by the RTA agent, only after processing the purchase and sales transactions, for which they need the applicable NAV. Therefore transactions can be processed only the next day based on NAV of previous day. After processing the transactions, the updated unit capital is communicated to the AMC.

All transactions are captured by RTA by day-end for next day’s reports to fund house for cash flow projection.

💡 NAV (Day T) = (Market value of scheme’s investments + current assets – current liabilities as on Day T) / (No. of units outstanding as on Day T-1)

## Time Stamping

SEBI has imposed electronic time stamping as a mandatory requirement for financial transactions related to mutual funds, for the same reason. All financial transactions are processed in the RTA system as per the applicable NAV according to the recorded time stamp on the document.

## Applicable NAV

The applicable NAV for a financial transaction is according to the time stamp. This eliminates uncertainty associated with financial transactions and brings in uniformity in their treatment.

The applicable NAV for a mutual fund transaction will depend upon:

* The day of the transaction
* The time of the transaction
* The type of scheme
* The availability of clear funds for utilization by the funds, without resorting to any credit facilities.

## Holding Units in Dematerialized Form

Mutual fund investors can choose to hold units in dematerialized form. The choice to hold units in demat mode is provided in the subscription form and the ISIN for each option of each scheme is quoted in the statement of account sent to the investors. This applies to new units purchased by investors as well as existing units represented by the statement of account.
