# Get Tracking History

Request for tracking history of a consignment

- Endpoint: /api/2.0/tracking
- Http Method: POST

*This API can only be called after the API authentication is approved (the correct
auth string has been passed). 

## Required Parameters:
* consignmentRef [Require, e.g. "00187037343"]

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
  "consignmentRef": "007862951562"
}
```

**Responses**
``` json
{
    "isSuccess": true,
    "data": {
        "carrierTrackingRef": "2541300295156201AKL025JN",
        "trackingInfos": [
            {
                "status": 7,
                "description": "Cancelled",
                "notes": "",
                "statusTime": ""
            }
        ]
    }
}
```
* carrierTrackingRef is the reference number for tracking in the carrier services.
* Return an empty trackingInfos if there are no any tracking.
