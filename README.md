# MobilePay PartnerBank API Documentation
This document describes the call structure to query PartnerBank API of MobilePay. The API is designed to be called by an integrator (ex. data center), representing a bank. The focal purpose of the API is to provide partnerbanks with data in order to monitor if and how their merchants are using MobilePay. 

Integrator needs to inform about GitHub username, in order to be invited to the documentation repository with read rights

This document is meant to be used by the developers integrating into the API.

## Support

If you have any questions, write to DeveloperSupport at developer@mobilepay.dk 

Received an error? Don’t worry! First, check your original request and try again. If you're still having problems, ask our support team for help.

MobilePay Sandbox Developer Portal is https://sandbox-developer.mobilepay.dk/ 

Production Developer Portal is https://developer.mobilepay.dk/ 

## Prerequisites
- **Create an user:** Once you have received an invitation to the Developer Portal, then you need to register as a new user within 7 days. 
- **Create an app:** From the developer portal, click on your e-mail in the top and choose ” My apps” at the top of the page. It shows a list of applications that the developer has created. Click the create new app button. Make a note of your `X-IBM-Client-Id` and `X-IBM-Client-Secret`. These are needed for your application to access the API.
- **Subscribe to API:** Integrator has subscribed to the PartnerBank API product on https://developer.mobilepay.dk/product 

## Data repository

The table shows the Products, the status and the PaymentPoint when calling the API 

| Product           | Current status                                                         | PaymentPoint |
| -------------------  | ------------------------------------------------------------------- | ------------------- |
| `MyShop`      | Data included on all merchants      | MobilePayNumber |
| `POS`  | Not in repository |Store |
| `Subscriptions` | Data included on all merchants                                                        |SubscriptionProvider |
| `Invoice` | Data included on all merchants                                                       |InvoiceIssuerID |
| `AppSwitch` | Not in repository                                                        |x |

## Request headers
After onboarding to https://developer.mobilepay.dk and creating an App, use the given `X-IBM-Client-Id` and `X-IBM-Client-Secret` as request headers when calling the API. 

To specify which bank you are representing during this call, add the Bank-Identifier-Code header. The header format is AAAABBCC:
- AAAA - identifies a bank;
- BB - identifies the country of the bank;
- CC - location code for head office.

| Header Key           | Description                                                         |
| -------------------  | ------------------------------------------------------------------- |
| `X-IBM-Client-Id`      | Client-Id of your App created in https://developer.mobilepay.dk     |
| `X-IBM-Client-Secret`  | Client-Secret of your App created in https://developer.mobilepay.dk |
| Bank-Identifier-Code | 8 symbol BIC                                                        |

Your `X-IBM-Client-Secret` will only be displayed once. If you forget or lose it, you can verify the secret to see if it’s correct or reset it to get a new one.
 

### Example
| Header Key           | Header Value                                       |
| -------------------  | -------------------------------------------------- |
| `X-IBM-Client-Id`      | 7a3b2df1-8824-4829-b308-32b799a39dfa               |
| `X-IBM-Client-Secret`  | F9zQ8oL2wW6aJ5lLasQ4hQ1jH4uL8oA6sD5cL3oU7aO1mP2nZ4 |
| `Bank-Identifier-Code` | DABADKKK                                           |


## API limitations
- The provided data is not real-time. The delay can be up to 48h.

## Endpoints
- [Technical documentation of all endpoints](endpoints.md)
