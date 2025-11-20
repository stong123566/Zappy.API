# Create a new consignment

Allows third-party systems to make consignments and get consignment tracking
numbers based on the passed QuoteRequestUuid and CarrierMethodId. 

- Endpoint: /api/2.0/consignmentcreate
- Http Method: POST

*This API can only be called after the API authentication is approved (the correct
auth string has been passed). 

## Required Parameters:
* QuoteRequestUuid [Require, value from /api/consignment/quote]
* CarrierMethodId [Require, value from /api/consignment/quote, e.g. "ft_freight"]
* ThirdPartyOrderIds [Optional, Third-party order ID]
* BatchConsignmentId [Optional, Batch Consignment Id]
* IsSignature [Optional, 0 - No Signature required; 1 - Signature required]
* IsATL [Optional, 0 - No Authority to leave; 1 - Authority to leave]
* EncryptedConsignmentRef [Optional, Encrypted consignmentRef]
* EmailLabel [Optional, Email a return link]
* AsendiaDropOffPointsId [Optional, Asendia Drop Off Points Id]
* 
