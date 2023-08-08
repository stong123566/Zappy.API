#  Get available shipping rates

Allows third-party systems to get a list of applicable shipping rate based on
the passed sender's address, recipient's address and parcel(s)’ dimensions.

- URL: https://api.parcelport.co.nz/api/2.0/rate
- Http Method: POST

*This API can only be called after the API authentication is approved (the correct
auth string has been passed).

## Required Parameters:
*isSignature* - [Optional, default is '*0*', '*1*' if signature required]

*isSaturday* - [Optional, default is '*0*', '*1*' if saturday delivery]

*parcels* - [Required, a list of parcel]
- **kind** - [Optional, default is '*0*', '*1*' if using satchel]
- **length** - [Required if not using satchel, length of the parcel cm]
- **width** - [Required if not using satchel, width of the parcel cm]
- **height** - [Required if not using satchel, height of the parcel cm]
- **weight** - [Required, weight of the parcel Kg]
- **satchelCode** - [Required if using satchel, see the following table of *Parcelport satchel list* ]
- **custRef** - [Optional reference of the item]
- **packageContents** - [Required if international, a list of item in the parcel]
  -- **description** [Required, description of item]

*deliveryAddress*
- **addressBody** [Require, unit number + street number + street name]
- **addressSuburb** [Require, suburb]
- **addressCity** [Require, city]
- **addressPostcode** [Require, postcode]
- **contactName** [Require, contact name]
- **addressUnit** [Optional, unit number]
- **addressBuilding** [Optional, building]
- **addressNumber** [Optional, street number]
- **addressStreet** [Optional, street name]
- **email** [Require, sender email]
- **phone** [Optional, contact phone]
- **companyName** [Optional, company name] 
- **instruction** [Optional, instruction]
- **addressLat** [Optional, latitude]
- **addressLng** [Optional, longitude]

*pickupAddress*
- **addressBody** [Require, unit number + street number + street name]
- **addressSuburb** [Require, suburb]
- **addressCity** [Require, city]
- **addressPostcode** [Require, postcode]
- **contactName** [Require, contact name]
- **addressUnit** [Optional, unit number]
- **addressBuilding** [Optional, building]
- **addressNumber** [Optional, street number]
- **addressStreet** [Optional, street name]
- **email** [Require, sender email]
- **phone** [Optional, contact phone]
- **companyName** [Optional, company name] 
- **instruction** [Optional, instruction]
- **addressLat** [Optional, latitude]
- **addressLng** [Optional, longitude]

*Parcelport satchel list*
<table>
  <tr>
    <th>Satchel name</th>
    <th>code</th>
  </tr>
  <tr>
    <td>Satchel 130x240 DLE Letter Size</td>
    <td>dle</td>
  </tr>
  <tr>
    <td>Satchel 185x280 A5 Size</td>
    <td>a5</td>
  </tr>
  <tr>
    <td>Satchel 250x325 A4 Size</td>
    <td>a4</td>
  </tr>
  <tr>
    <td>Satchel 275x380 Foolscap Size</td>
    <td>fs</td>
  </tr>
  <tr>
    <td>Satchel 325x440 A3 Size</td>
    <td>a3</td>
  </tr>
  <tr>
    <td>Satchel 395x440 Lineflow Size</td>
    <td>lf</td>
  </tr>
  <tr>
    <td>Satchel 445x440 Extra Large Size</td>
    <td>xl</td>
  </tr>
  <tr>
    <td>Satchel 450x610 A2 Size</td>
    <td>a2</td>
  </tr>
</table>

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
  "parcels": [
    {
      // "kind": "1",
      // "satchelCode": "a4",
      "length": "20",
      "height": "20",
      "width": "30",
      "weight": "0.5",
      "custRef": "09-2101-00021"
    }
  ],
  "deliveryAddress": {
    "addressBody": "17 Witbrock Crescent",
    "addressCity": "Christchurch",
    "addressPostcode": "8053",
    "addressSuburb": "Burnside",
    "contactName": "Alice",
    "email": "Alice@gmail.com",
    "phone": "+64 09 234567"
  },
  "pickupAddress": {
    "addressBody": "12 Pitt Street",
    "addressCity": "Auckland",
    "addressPostcode": 1010,
    "addressSuburb": "Auckland Central",
    "contactName": "test",
    "email": "services@parcelport.co",
    "phone": "+64 09 234567",
    "mobile": "02101020304"
  }
}
```
**Responses**  
A JSON encoded string contains all valid shipping rates with a price and a shipping method id.  
The rates will be expired in 15 minutes.  
Choose a carrier from the list of rate and [create a consignment](Consignment/README.md) using it's carrierMethodId and the quoteRequestId.

``` json
{
    "isSuccess": true,
    "data": {
        "quoteRequestId": "b70c310e-4838-4115-837f-b167250d3324",
        "expiryDate": "2022-09-20T11:56:10.8279273+12:00",
        "rates": [
            {
                "carrierName": "Post Haste",
                "carrierMethodId": "phms",
                "totalPrice": 4.63
            },
            {
                "carrierName": "Castle Parcels",
                "carrierMethodId": "cplw",
                "totalPrice": 4.63
            },
            {
                "carrierName": "CourierPost",
                "carrierMethodId": "CPOLP",
                "totalPrice": 3.82
            }
        ],
        "errors": {
            "post Haste Api": [
                "Please check the errors collection if available to help identify which request data is incorrect"
            ],
            "castle Parcel Api": [
                "Please check the errors collection if available to help identify which request data is incorrect"
            ],
            "precise": [
                "The min size of the parcel is 25kg or 0.125m³."
            ]
        }
    }
}
```

***

