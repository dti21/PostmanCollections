# **Introduction**
#### Welcome to the Transactions Sandbox API.

------------------------------------------------------------------------------------------

### The API
This API provides a standard RESTful interface that enables a user to
* Get all the transactions specified by account and bank
* Get the details of a specific transaction

> Visit https://developer.nbg.gr/documentation/transactions-api-oauth2-v1-4
> for the full API documentation

### Real life Use Case Scenario

The main functionality of the application is to aggregate financial data for the cards of a user.

First of all, we will create our sandbox by making an **HTTP POST** request to the following URL
> https://apis.nbg.gr/public/sandbox/obp.transaction.sandbox.oauth2.api/sandbox

With a request body:
```
 {
   "sandbox_id": "DE2A6935-9162-4076-B160-B5D3069DAE45"
 }
``` 

**Note: Remember to store *sandbox_id* somewhere in your application, because you will need to provide it in as a header
in each api call.**

When the user selects the bank to get their transactions from,the account and the view, a **HTTP POST** request to the following endpoint:
>https://apis.nbg.gr/public/sandbox/obp.transaction.sandbox.oauth2.api/obp/banks/{bank_id}/accounts/{account_id}/{view_id}/transactions/details

along with a request body:

{
  "tranId": "0b30f879-cd0b-49bc-b474-39e2bbb89395",
  "remTpe":"SEPA"
}

will return the results below:


{
    "transactionId": "0b30f879-cd0b-49bc-b474-39e2bbb89395",
    "ordererBankBic": "ETHNGRAA",
    "ordererName": "sDoulfis",
    "ordererAccountNo": "97226400154",
    "ordererIban": "GR0901109720000097226400154",
    "benAccountNo": "10348012377",
    "benIban": "GR4501101030000010348012377",
    "benName": [
        "User2"
    ],
    "remAmount": -20,
    "commision": null,
    "chargesAmount": null,
    "chargesXt": null,
    "chargesMsg": null,
    "valeur": "2018-11-30T00:00:00+02:00",
    "issueDate": "2018-11-29T00:00:00+02:00",
    "description": "",
    "remStatus": "Pending",
    "remMsg": []
}

Created by **NBG**. 
See more at https://www.nbg.gr/