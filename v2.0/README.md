# ParcelPort System API(v2.0)

Parcel Port API provides an access to enable your customer to send parcels using our system.

***

### Live URL: https://api.parcelport.co.nz  

# Get token
Allows third-party systems to get Payport customers’ API authorization token from Payport System. The token will expire in 30Mins

URL: https://api.parcelport.co.nz/token
Http Method: POST

## Required Parameters:
* username [Require]
* password [Require]
* grant_type [Require] [Must be 'password']

## Example
Request 
POST https://api.parcelport.co.nz/token

**Headers**
Content-Type: application/json;

**x-www-form-urlencoded**
``` json
{
    username:"Test"
    password:"Password"
    grant_type: "password"
}
```

**Responses**
``` json
{
    "isSuccess": true,
    "accessToken": "XlES6IXxqQZwo37CoB9ydlZmWQV84VdNhv-MF0WXpr9SUJqv3bL5CsBIDTqrDildBRBkzo6J2VmbdGyZu7yBGANnCUVMDzxelycDQXn9xBxqobDBAVs70nslc4C90PJ6jmtEI56U5SD8ms5c7ubKOa6DR0rLb_GTY4kXitqHPsPpCaUKckwGSIyCwGeZcAx60A50Na2CTISg5CfCGFTTAOQ6znVRLkJIb4fbbI87iYkBLDbQb2S09iFAqMc0odR9lpziU3BS5y41fZBXHwUUCEwk2-EFs7RFS_L6WT0zRcBSlwluqGchGuiLCg7d3NT1bZEPcf8u_BQFc_Wnkjd_pf4RHdt7pBHa6mgDib5ao1hugdE5z",
    "access_token": "XlES6IXxqQZwo37CoB9ydlZmWQV84VdNhv-MF0WXpr9SUJqv3bL5CsBIDTqrDildBRBkzo6J2VmbdGyZu7yBGANnCUVMDzxelycDQXn9xBxqobDBAVs70nslc4C90PJ6jmtEI56U5SD8ms5c7ubKOa6DR0rLb_GTY4kXitqHPsPpCaUKckwGSIyCwGeZcAx60A50Na2CTISg5CfCGFTTAOQ6znVRLkJIb4fbbI87iYkBLDbQb2S09iFAqMc0odR9lpziU3BS5y41fZBXHwUUCEwk2-EFs7RFS_L6WT0zRcBSlwluqGchGuiLCg7d3NT1bZEPcf8u_BQFc_Wnkjd_pf4RHdt7pBHa6mgDib5ao1hugdE5z",
    "expiresIn": 86399,
    "tokenType": "bearer"
}
```

***

# Get rates
- **[<code style="background-color:#009D77">POST</code> /api/2.0/rate](Rate/README.md)** returns a list of rate

# Make a consignment
- **[<code style="background-color:#E97500">POST</code> /api/2.0/consignment](Consignment/README.md)** Make a consignment

# Label
- **[<code style="background-color:#1391FF">POST</code> /api/2.0/label](Label/README.md)** Get a url of label(PDF)

# Booking
- **[<code style="background-color:#009D77">POST</code> /api/2.0/booking](Booking/README.md)** Booking a pickup time

# Tracking
- **[<code style="background-color:#1391FF">POST</code> /api/2.0/tracking](Tracking/README.md)** Get tracking history of the consignment
