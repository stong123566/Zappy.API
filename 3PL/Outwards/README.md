# Create a new outwards request

Create an outwards request via this endpoint.  
Once created, it will appear in our system and be processed by our warehouse staff.

- URL: /Outwards
- Http Method: POST

*This API can only be called after the API authentication is approved (the correct
auth string has been passed). 

## Required Parameters:
*ReferencNumber* - [Required, a unique string to identify the outwards order]  
*Notes* - [Optional]  
*DateOrder* - [Optional, format: '*yyyy-MM-dd*', default is '*Today*']  
*NeedDelivery* - [Required, '*0*' - pickup, '*1*' - delivery]  
*RecipientName* - [Required]  
*RecipientCompanyName* - [Optional]  
*RecipientPhone* - [Optional]  
*RecipientEmail* - [Optional]  
*RecipientAddressStreet* - [Required if delivery]  
*RecipientAddressSuburb* - [Required if delivery]  
*RecipientAddressCity* - [Required if delivery]  
*RecipientAddressStreet* - [Required if delivery]  
*RecipientAddressState* - [Optional, it is relvant to the country]  
*RecipientAddressPostcode* - [Required if delivery]  
*RecipientAddressCountry* - [Required if delivery]  
*RecipientInstruction* - [Optional]  
*OutwardsItems* - [Required, a list of outwards item]
- **ProductName** - [Optional]
- **Barcode** - [Required, must be defined in our system]
- **Sku** - [Optional]
- **Quantity** - [Required]
- **Notes** - [Optional]


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
    "ReferencNumber": "2024-01-30-0002",
    "Notes": "Test importing an outwards order via the API",
    "DateOrder": "2024-01-30",
    "NeedDelivery": "1",
    "RecipientName": "Kevin",
    "RecipientCompanyName": "Parcelport",
    "RecipientPhone": "02102635254",
    "RecipientEmail": "customservice@parcelport.co.nz",
    "RecipientAddressStreet": "39 Mahara Avenue",
    "RecipientAddressSuburb": "Birkenhead",
    "RecipientAddressCity": "Auckland",
    "RecipientAddressState": "",
    "RecipientAddressPostcode": "0626",
    "RecipientAddressCountry": "NZ",
    "RecipientInstruction": "Pls left it in the front of the door.",
    "OutwardsItems": [
        {
            "ProductName": "innerBox：test a vvvvvvvvvvvvvvvvvvvvvvvvvvvvvvvvvvvvvery long product name",
            "Barcode": "i1",
            "Sku": "",
            "Quantity": 5,
            "Notes": ""
        },
        {
            "ProductName": "Outer Box: test 'duplicate'",
            "Barcode": "o2",
            "Sku": "",
            "Quantity": 1,
            "Notes": ""
        }
    ]
}
```

**Responses**
A success response will only include a flag 'IsSuccess' with a value 'True'.

``` json
{
    "IsSuccess": true
}
```

An error response will include a 'StatusCode' and a list of error messages, labeled as 'Errors'.

``` json
{
    "IsSuccess": false,
    "StatusCode": 400,
    "Errors": [
        "Duplicated reference number. "
    ]
}
```
