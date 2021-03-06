# **Introduction**
#### Welcome to ibankPay Sandbox
------------------------------------------------------------------------------------------

### A few words about i-bank Pay
i-bank Pay is the multi-award winning wallet by National Bank of Greece that is used to:
- send money to your friends and make payments and purchases with your phone
- make money transfers between your friends
- pay businesses and professionals

### The API
This API provides a standard RESTful interface that enables a user to
- Perform money transfers to another member or merchant or even make donations by just  **registering as a Member**  to our service and verifying your mobile device as a trusted one. 
- Once the registration step is completed simply  **select the other member**  you wish to  **send money to or request money from or pay**  and pretty much that's it.
> Visit https://microsites.nbg.gr/developer/documentation/ibank-Pay-Sandbox-v13-4004
>for the full API documentation
> 
### Real life Use Case Scenario
Given that you are out with your friends at a restaurant and the waiter doesn't have change for everyone, one friend pays the whole bill. Then he suggests that you can give your share via i-bank Pay. 
All you have to do is download i-bank pay App, make a registration, discover your friends from your contact list and pay them.
In this scenario we will be using the API to register as a member and perform a P2P payment.

#### How do I make a registration?
First of all, we will create our sandbox by making an **HTTP POST** request to the following URL
>https://microsites.nbg.gr/api.gateway/sandbox/ibankpay/headers/v1.3/sandbox

With a request body:
```
 {
   "sandbox_id": "5DE11422-D7D5-4727-82FA-0C26F195C66C"
 }
``` 

**Note: Remember to store *sandbox_id* somewhere in your application, because you will need to provide it in as a header in each api call.**

Then, you have to create a sandbox user by making an **HTTP POST** request to the following URL
>https://microsites.nbg.gr/api.gateway/sandbox/ibankpay/headers/v1.3/sandbox/{sandbox_id}/users

In order to register a member you have to make an **HTTP POST** request to the following URL
>https://microsites.nbg.gr/api.gateway/sandbox/ibankpay/headers/v1.3/P2P/registerMember

To complete the registration you have to verify the device by making an **HTTP POST** request to the following URL
>https://microsites.nbg.gr/api.gateway/sandbox/ibankpay/headers/v1.3/P2P/verifyDeviceRegistration
  
#### How do I send money?

Find from your list of contacts the members that use i-bank Pay with an **HTTP POST** request to the following URL
https://microsites.nbg.gr/api.gateway/sandbox/ibankpay/headers/v1.3/P2P/discoverMemberV2

Then invoke an **HTTP POST** request to the following URL to complete the payment
>https://microsites.nbg.gr/api.gateway/sandbox/ibankpay/headers/v1.3/P2P/payV2

Created by **NBG**. 
See more at https://www.nbg.gr/