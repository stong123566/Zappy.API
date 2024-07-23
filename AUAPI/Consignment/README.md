# Create a new consignment

Allows third-party systems to make consignments and get consignment tracking
numbers based on the passed QuoteRequestUuid and CarrierMethodId. 

- Endpoint: /api/consignment/create
- Http Method: POST

*This API can only be called after the API authentication is approved (the correct
auth string has been passed). 

## Required Parameters:
* QuoteRequestUuid [Require, value from /api/consignment/quote]
* CarrierMethodId [Require, value from /api/consignment/quote, e.g. "ft_freight"]

*Parcels* - [Required, a list of parcel]
- **PackageId** - [Optional, default is '**', see the following table of *Zappy satchel list* ]
- **Length** - [Required if not using satchel, length of the parcel cm]
- **Width** - [Required if not using satchel, width of the parcel cm]
- **Height** - [Required if not using satchel, height of the parcel cm]
- **Weight** - [Required, weight of the parcel Kg]
- **ItemRef** - [Optional reference of the item]
- **ItemNo** - [Required index of the item]

*RecipientAddress*
- **AddressStreet** [Require, unit number + street number + street name]
- **AddressSuburb** [Require, suburb]
- **AddressCity** [Require, city]
- **AddressPostcode** [Require, postcode]
- **AddressCountry** [Require, country]
- **ContactName** [Require, contact name]
- **AddressUnit** [Optional, unit number]
- **AddressBuilding** [Optional, building]
- **Email** [Require, sender email]
- **Phone** [Optional, contact phone]
- **CompanyName** [Optional, company name] 
- **Instruction** [Optional, instruction]
- **IsCommercialAddress** [Optional, is commercial address, default is '*0*', '*1*' if commercial address]

*SenderAddress*
- **AddressStreet** [Require, unit number + street number + street name]
- **AddressSuburb** [Require, suburb]
- **AddressCity** [Require, city]
- **AddressPostcode** [Require, postcode]
- **AddressCountry** [Require, country]
- **ContactName** [Require, contact name]
- **AddressUnit** [Optional, unit number]
- **AddressBuilding** [Optional, building]
- **Email** [Require, sender email]
- **Phone** [Optional, contact phone]
- **CompanyName** [Optional, company name] 
- **Instruction** [Optional, instruction]
- **IsCommercialAddress** [Optional, is commercial address, default is '*0*', '*1*' if commercial address]

*Booking*
- **PickupOption** [Optional, 0 or 1, default 0 for booking later, 1 if booking now]
- **PickupDate** [Optional, default DateTime.Now]


## Example

**Request Headers**
```
Content-Type: application/json;
```

**Request Authorization**
```
Bearer:XlES6IXxqQZwo37CoB9ydlZmWQV84VdNhv-MF0WXpr9SUJqv3bL5CsBIDTqrDildBRBkzo6J2VmbdGyZu7yBGANnCUVMDzxelycDQXn9xBxqobDBAVs70nslc4C90PJ6jmtEI56U5SD8ms5c7ubKOa6DR0rLb_GTY4kXitqHPsPpCaUKckwGSIyCwGeZcAx60A50Na2CTISg5CfCGFTTAOQ6znVRLkJIb4fbbI87iYkBLDbQb2S09iFAqMc0odR9lpziU3BS5y41fZBXHwUUCEwk2-EFs7RFS_L6WT0zRcBSlwluqGchGuiLCg7d3NT1bZEPcf8u_BQFc_Wnkjd_pf4RHdt7pBHa6mgDib5ao1hugdE5z
```

**Request Body**
``` json
{
    "QuoteRequestUuid": "7084b2c573e94628a09fde007fd39914",
    "CarrierMethodId": "ft_freight",
    "SenderAddress": {
        "AddressUnit": "",
        "AddressBuilding": "",
        "AddressStreet": "12 Pitt Street",
        "ContactName": "Kevin",
        "CompanyName": "Zapy",
        "AddressSuburb": "Parramatta",
        "AddressCity": "Parramatta",
        "AddressState": "NSW",
        "AddressCountry": "AU",
        "AddressPostcode": "2150",
        "Phone": "2102607358",
        "Email": "kevin.h@shipzappy.com",
        "Instruction": "",
        "IsCommercialAddress": "0"
    },
    "RecipientAddress": {
        "AddressUnit": "",
        "AddressBuilding": "",
        "AddressStreet": "450 Nepean Highway",
        "ContactName": "to",
        "CompanyName": "",
        "AddressSuburb": "Mount Martha",
        "AddressCity": "Mount Martha",
        "AddressState": "VIC",
        "AddressCountry": "AU",
        "AddressPostcode": "3934",
        "Phone": "123456",
        "Email": "www@qq.com",
        "Instruction": "123ert",
        "IsCommercialAddress": "0"
    },
    "Parcels": [
        {
            "ItemNo": 1,
            "PackageId": "",
            "Length": "1",
            "Width": "1",
            "Height": "1",
            "Weight": "1",
            "ItemRef": ""
        }
    ],
    "Booking": {
        "PickupOption": "0"
    }
}
```

**Responses**
A JSON encoded string contains all the valid shipping methods with shipping method ids.
The requestID need to be added in the request when you create a consignment, and it will be expired.

``` json
{
    "IsSuccess": true,
    "Data": {
        "Success": true,
        "ErrorMessage": null,
        "ConsignmentRef": "000020000040",
        "ConsignmentId": null,
        "InfoMessage": null
    }
}
```

***
