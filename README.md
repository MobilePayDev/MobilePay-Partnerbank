# MobilePay PartnerBank API Documentation
This document describes the call structure to query PartnerBank API of MobilePay. The API is designed to be called by an integrator (ex. data center), representing a bank. This document is meant to be used by the developers integrating into the API.

## Prerequisites
- Integrator has been onboarded to https://developer.mobilepay.dk/ and has an App subscribed to the PartnerBank API product.

## Request headers
After onboarding to https://developer.mobilepay.dk and creating an App, use the given Client-Id and Client-Secret as request headers when calling the API.

To specify which bank you are representing during this call, add the Bank-Identifier-Code header. The header format is AAAABB:
- AAAA - identifies a bank;
- BB - identifies the country of the bank.

| Header Key           | Description                                                         |
| -------------------  | ------------------------------------------------------------------- |
| X-IBM-Client-Id      | Client-Id of your App created in https://developer.mobilepay.dk     |
| X-IBM-Client-Secret  | Client-Secret of your App created in https://developer.mobilepay.dk |
| Bank-Identifier-Code | 8 symbol BIC                                                        |

### Example
| Header Key           | Header Value                                       |
| -------------------  | -------------------------------------------------- |
| X-IBM-Client-Id      | 7a3b2df1-8824-4829-b308-32b799a39dfa               |
| X-IBM-Client-Secret  | F9zQ8oL2wW6aJ5lLasQ4hQ1jH4uL8oA6sD5cL3oU7aO1mP2nZ4 |
| Bank-Identifier-Code | DABADKKK                                           |


## API limitations
- The provided data is not real-time. The delay can be up to 48h.

## Endpoints
- [Technical documentation of all endpoints](endpoints.md)
