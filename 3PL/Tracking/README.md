# Get Tracking History

Request for tracking history of an outwards order.

- URL: /Outwards/{ReferencNumber}
- Http Method: GET

*This API can only be called after the API authentication is approved (the correct
auth string has been passed). 

## Required Parameters:
* ReferencNumber [Require, the '*ReferenceNumber*' passed while creating the outwards request]

## Response：
*Data* - [A Json Object]
- **ProcessStatus** - [Refer to the 'Process Status code table' below]
- **StatusDescription** - [A description for 'ProcessStatus']
- **Tracking** - [A list of tracking information]
  - **Carrier** 
  - **TrackingRef**
  - **TrackingLink**
*Process Status code table*
<table>
  <tr>
    <th>Process Status Code</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>0</td>
    <td>The outwards request has not been submitted yet. Only if the outwards request is created on the client-side pages.</td>
  </tr>
  <tr>
    <td>1</td>
    <td>The outwards is waiting to be processed. The default status if the outwards request is created via API</td>
  </tr>
  <tr>
    <td>3</td>
    <td>The outwards is currently being processed.</td>
  </tr>
  <tr>
    <td>6</td>
    <td>The outwards has been picked up.</td>
  </tr>
  <tr>
    <td>9</td>
    <td>The outwards has been cancelled.</td>
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

**Responses**
``` json
{
    "IsSuccess": true,
    "Data": {
        "ProcessStatus": "1",
        "StatusDescription": "The outwards is currently being processed.",
        "Tracking": []
    }
}
```