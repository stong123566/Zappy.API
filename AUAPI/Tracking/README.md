# Get Tracking History

Request for tracking history of a consignment

- Endpoint: /api/consignment/trackinghistory/{consignmentRef}
- Http Method: GET

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

**Request**
```
https://uat-api.zappy.au/api/consignment/trackinghistory/00187037343
```

**Responses**
``` json
{
    "IsSuccess": true,
    "Data": {
        "Success": true,
        "ErrorMessage": null,
        "DataList": [
            {
                "ConsignmentStatusId": 4,
                "StatusDate": "2024-07-10T09:49:30",
                "Description": "Your parcel has been delivered according to delivery instructions."
            },
            {
                "ConsignmentStatusId": 12,
                "StatusDate": "2024-07-10T05:33:10",
                "Description": "Your parcel is with your local courier and ready for delivery."
            },
            {
                "ConsignmentStatusId": 12,
                "StatusDate": "2024-07-09T15:19:57",
                "Description": "Your parcel has been received at Sydney depot."
            },
            {
                "ConsignmentStatusId": 3,
                "StatusDate": "2024-07-09T12:20:06",
                "Description": "Your parcel has been picked up by one of our couriers."
            }
        ]
    }
}
```
* carrierTrackingRef is the reference number for tracking in the carrier services.
* Return an empty trackingInfos if there are no any tracking.
