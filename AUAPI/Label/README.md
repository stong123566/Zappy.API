# Get label

Request for getting a URL to download the label in PDF from our main site https://ship.zappy.au/.

*This API can only be called after the API authentication is approved (the correct
auth string has been passed). 

- Endpoint: /api/consignment/label/{consignmentRef}
- Http Method: GET

## Required Parameters:
* consignmentRef [Require, value from /api/consignment/create, e.g. "000020000037"]

## Example

**Request Headers**
```
Content-Type: application/json;
```

**Request Authorization**
```
Bearer:XlES6IXxqQZwo37CoB9ydlZmWQV84VdNhv-MF0WXpr9SUJqv3bL5CsBIDTqrDildBRBkzo6J2VmbdGyZu7yBGANnCUVMDzxelycDQXn9xBxqobDBAVs70nslc4C90PJ6jmtEI56U5SD8ms5c7ubKOa6DR0rLb_GTY4kXitqHPsPpCaUKckwGSIyCwGeZcAx60A50Na2CTISg5CfCGFTTAOQ6znVRLkJIb4fbbI87iYkBLDbQb2S09iFAqMc0odR9lpziU3BS5y41fZBXHwUUCEwk2-EFs7RFS_L6WT0zRcBSlwluqGchGuiLCg7d3NT1bZEPcf8u_BQFc_Wnkjd_pf4RHdt7pBHa6mgDib5ao1hugdE5z
```

**Request**
```
https://uat-api.zappy.au/api/consignment/label/000020000037
```

**Responses**
``` json
{
    "IsSuccess": true,
    "Data": {
        "Success": true,
        "ErrorMessage": null,
        "LabelUrl": "https://au-parcelport-uat.s3.ap-southeast-2.amazonaws.com/Label/Aramex/000020000037.pdf"
    }
}
```
