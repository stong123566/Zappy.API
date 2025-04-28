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

*Zappy Consignment Status list*
<table>
  <tr>
    <th>Code</th>
    <th>Name</th>
    <th>Description</th>
  </tr>
  <tr>
  <td>0</td>
  <td>Consignment Created</td>
  <td>Consignment Created</td>
  </tr>
  <tr>
  <td>1</td>
  <td>Pick Up Requested</td>
  <td>Pick up request received</td>
  </tr>
  <tr>
  <td>2</td>
  <td>Scheduled for Pickup</td>
  <td>Pick Up Request Booked</td>
  </tr>
  <tr>
  <td>3</td>
  <td>Picked Up</td>
  <td>Picked Up</td>
  </tr>
  <tr>
  <td>4</td>
  <td>Delivered</td>
  <td>Delivered</td>
  </tr>
  <tr>
  <td>5</td>
  <td>Debit</td>
  <td>Debit</td>
  </tr>
  <tr>
  <td>7</td>
  <td>Cancelled</td>
  <td>Cancelled</td>
  </tr>
  <tr>
  <td>8</td>
  <td>On Board</td>
  <td>On Board</td>
  </tr>
  <tr>
  <td>9</td>
  <td>Non Delivery</td>
  <td>Non Delivery</td>
  </tr>
  <tr>
  <td>10</td>
  <td>Association</td>
  <td>Parcel is with partner courier</td>
  </tr>
  <tr>
  <td>11</td>
  <td>Status</td>
  <td>Parcel is at depot</td>
  </tr>
  <tr>
  <td>12</td>
  <td>Credit</td>
  <td>Credit</td>
  </tr>
  <tr>
  <td>13</td>
  <td>Delivery Confirmed</td>
  <td>Delivery is confirmed without scan</td>
  </tr>
  <tr>
  <td>14</td>
  <td>Driver Been</td>
  <td>Driver been for pick up, scan maybe pending</td>
  </tr>
  <tr>
  <td>404</td>
  <td>Waiting For Proccess</td>
  <td>It can take up to an hour for a shipment to appear</td>
  </tr>
  <tr>
  <td>-1</td>
  <td>In Transit</td>
  <td>In Transit</td>
  </tr>
  <tr>
  <td>15</td>
  <td>Booked already</td>
  <td>Booked already</td>
  </tr>
  <tr>
  <td>99</td>
  <td>System Error</td>
  <td>System Error</td>
  </tr>
  <tr>
  <td>16</td>
  <td>Unpaid</td>
  <td>Consignment unpaid</td>
  </tr>
  <tr>
  <td>17</td>
  <td>Hand Over</td>
  <td>Delivery Handed Over</td>
  </tr>
  <tr>
  <td>18</td>
  <td>Partially Delivered</td>
  <td>Partially Delivered</td>
  </tr>
</table>


