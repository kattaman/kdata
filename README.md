# Kdata
Kdata is a JSON format and API used by KattHub to communicate measures and commands.

## What is KattHub?

KattHub aims to create a uniform standard, both in API and format, to communicate measures and commands to and from smart devices.

### Current version

The current version is K0

### KData format
The JSON Kdata format is:

```json
{
  "timestamp": "2015-01-01T06:51:18.108Z",
  "dataId": "PWRABS",
  "dataSubId": "0001"
  "command": "INFO",
  "value": 19,
  "version": "K0"
  "coordinates": {
    "latitude": 45.464161,
    "longitude": 9.190336
    }
 }
```

with the fields:

#### deviceId	
- Type: String
- Optional: false
- Description: Device unique ID.

#### timestamp	
- Type: String
- Optional: false
- Description: Timestamp of Kdata (ISO 8601).

#### dataId	
- Type: String
- Optional: false
- Description: DataID of Kdata. The value must be one of the managed dataIds.

#### dataSubId
- Type: String
- Optional: false (default: '0001' )
- Description: DataSubID of Kdata.

#### command	
- Type: String
- Optional: false
- Description: Kdata command (only INFO at the moment).

#### value	
- Type: Number
- Optional: false
- Description: Value of Kdata.

#### version	
- Type: String
- Optional: false
- Description: Kdata version used (K0 at the moment).

#### coordinates	
- Type: Object
- Optional: true
- Description: Actual coordinates of device sending Kdata.

##### latitude	
- Type: Number
- Optional: true
- Description: Latitude of device sending Kdata.

##### longitude	
- Type: Number
- Optional: true
- Description: Longitude coordinates of device sending Kdata.

### API
The API has version 1.0.0 version, compatible with Kdata R0, can be found at http://www.katthub.com/doc/api.html .
It supports the methods: GET, POST, PUT, DELETE

An example of use is:

```bash
$ curl -I "http://hub.katthub.com/api/v1/testme"
HTTP/1.1 200 OK
[NO AUTH] Hey! It works!
```
