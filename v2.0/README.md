# ParcelPort System API(v2.0)

Parcel Port API provides an access to enable your customer to send parcels using our system.

***

### Live URL: https://api.parcelport.co.nz  

# Get token
Allows third-party systems to get Payport customers’ API authorization token from Payport System. The token will expire in 30Mins

- URL: https://api.parcelport.co.nz/token
- Http Method: POST

## Required Parameters:
- username [Required]
- password [Required]
- grant_type [Required, must be '*password*']

## Example
**Request Headers**
```
Content-Type: application/json;
```

**x-www-form-urlencoded**
```
username=yourusername&password=yourpassword&grant_type=password
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

# Get token using client credentials
Log in to the Parcelport website first. Then, add your client credentials on the 'Settings -> API Secret Key' page. 
Utilize the added 'ClientId' and 'Secret' to obtain the access token through the following URL:   
https://api.parcelport.co.nz/token

## Required Parameters:
- client_id [Required]
- client_secret [Required]
- grant_type [Required, must be '*client_credentials*']

## Example
Request 
POST https://api.parcelport.co.nz/token

**Headers**
```
Content-Type: application/json;
```

**x-www-form-urlencoded**
``` json
{
    "client_id":"XlES6IXxqQZwo37CoB9ydlZmWQV84VdNhv",
    "client_secret":"GyZu7yBGANnCUVMDzxelycDQXn9xBxqobDBAVs70nslc4C90PJ6jmtEI56U5SD8ms5c7ubKOa6D==",
    "grant_type": "client_credentials"
}
```

**Responses**
``` json
{
    "isSuccess": true,
    "accessToken": "XlES6IXxqQZwo37CoB9ydlZmWQV84VdNhv-MF0WXpr9SUJqv3bL5CsBIDTqrDildBRBkzo6J2VmbdGyZu7yBGANnCUVMDzxelycDQXn9xBxqobDBAVs70nslc4C90PJ6jmtEI56U5SD8ms5c7ubKOa6DR0rLb_GTY4kXitqHPsPpCaUKckwGSIyCwGeZcAx60A50Na2CTISg5CfCGFTTAOQ6znVRLkJIb4fbbI8iYkBLDbQb2S09iFAqMc0odR9lpziU3BS5y41fZBXHwUUCEwk2-EFs7RFS_L6WT0zRcBSlwluqGchGuiLCg7d3NT1bZEPcf8u_BQFc_Wnkjd_pf4RHdt7pBHa6mgDib5ao1hugdE5z",
    "access_token": "XlES6IXxqQZwo37CoB9ydlZmWQV84VdNhv-MF0WXpr9SUJqv3bL5CsBIDTqrDildBRBkzo6J2VmbdGyZu7yBGANnCUVMDzxelycDQXn9xBxqobDBAVs70nslc4C90PJ6jmtEI56U5SD8ms5c7ubKOa6DR0rLb_GTY4kXitqHPsPpCaUKckwGSIyCwGeZcAx60A50Na2CTISg5CfCGFTTAOQ6znVRLkJIb4fbbI8iYkBLDbQb2S09iFAqMc0odR9lpziU3BS5y41fZBXHwUUCEwk2-EFs7RFS_L6WT0zRcBSlwluqGchGuiLCg7d3NT1bZEPcf8u_BQFc_Wnkjd_pf4RHdt7pBHa6mgDib5ao1hugdE5z",
    "expiresIn": 86399,
    "tokenType": "bearer"
}
```

***

# Get rates
- **[<code style="background-color:#009D77">POST</code> /api/2.0/rate](Rate/README.md)** returns a list of rate

# Create a consignment
- **[<code style="background-color:#009D77">POST</code> /api/2.0/consignment](Consignment/README.md)** Create a consignment

# Download label
- **[<code style="background-color:#009D77">POST</code> /api/2.0/label](Label/README.md)** Get a url of label(PDF)

# Booking pickup
- **[<code style="background-color:#009D77">POST</code> /api/2.0/booking](Booking/README.md)** Booking a pickup time

# Tracking
- **[<code style="background-color:#009D77">POST</code> /api/2.0/tracking](Tracking/README.md)** Get tracking history of the consignment
