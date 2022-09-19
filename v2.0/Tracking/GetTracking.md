# Get Tracking History

Request for tracking history of a consignment

*This API can only be called after the API authentication is approved (the correct
auth string has been passed). 

URL: https://api.parcelport.co.nz/api/1.0/tracking?consignmentRef={consignmentRef}&client_id={clientId}

## Required Parameters:
* consignmentRef [Require, e.g. "00187037343"]
* client_id [Require, e.g. "786"]

## Example
Request
GET https://api.parcelport.co.nz/api/1.0/tracking?consignmentRef=001870375905&client_id=786

**Headers**
Content-Type: application/json;

**Authorization**
Bearer:bSEX9PltRH8uoHLmFdnt115OqEPPQTrrHpht6Bwq0yos9EW7o6vcBtrV23AF2TcuA8FJTabH_t9x2hDo_tP840QIXfUmg0AGmRBfRHfeTeCjBGrK4ezMuLQ0jsyoDAb3cxUhkMniuJHYfSWhKlvyuQZPDqAffr4ggCY9qiojTgRm1s-EubJZK941SrtXBmTQKnkAWcru5MmXQvm0ziNAfZ_JhCKGoNHhpmnJVfQvGYMQNjMRknoE6GZl63GFZZ9tjMz2ICBPqEJsX67fWOoB2adbr58hA72omCMgLaX-1-DhYjlEnb_qhGljklPL3Qo6ohgykA

**Responses**
``` json
[
    {
        "consignment_ref": "0000000000000",
        "carrier_tracking_ref": "00000000000000000",
        "status": 4,
        "description": "Delivered",
        "notes": "Delivery",
        "status_time": "2022-06-13T07:40:20.573"
    },
    {
        "consignment_ref": "0000000000000",
        "carrier_tracking_ref": "00000000000000000",
        "status": 11,
        "description": "Parcel is at depot",
        "notes": "Parcel Sortation",
        "status_time": "2022-06-13T01:22:02"
    },
    {
        "consignment_ref": "0000000000000",
        "carrier_tracking_ref": "00000000000000000",
        "status": 11,
        "description": "Parcel is at depot",
        "notes": "Parcel Sortation",
        "status_time": "2022-06-11T11:36:55"
    },
    {
        "consignment_ref": "0000000000000",
        "carrier_tracking_ref": "00000000000000000",
        "status": 3,
        "description": "Picked up",
        "notes": "Acceptance",
        "status_time": "2022-06-10T16:26:20.14"
    }
]
```
* consignment_ref is only worked with Parcelport services.
* carrier_tracking_ref is the reference number for tracking in the carrier services.
* Return an empty result if there are no any tracking.
