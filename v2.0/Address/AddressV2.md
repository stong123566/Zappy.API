# Get address information based on keywords

- Endpoint: api/2.0/address
- Http Method: POST

## Required Parameters:
*Keyword* - [Required,The minimum length for a keyword is 5 characters]

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
    "Keyword":"8 Test"
}

```

Responses A JSON encoded string.
``` json

{
    "isSuccess": true,
    "data": {
        "count": 1,
        "addresses": [
            {
                "fullAddress": "8 Testacea Lane, Papamoa Beach, Papamoa 3118",
                "postcode": "3118",
                "suburb": "Papamoa Beach",
                "town": "Papamoa"
            }
        ]
    }
}

```

***
