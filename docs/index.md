## Summary
In this document we’re gonna show you how to make your HTTP API call to SenseCAP MX HTTP API.

## HTTP HOST
- https://status.sensecapmx.cloud

## Device Detail
**Get the detail of devices**

- path: {host}/api/openapi/device/view_device
- method: GET
- params:
    - api_key: apikey of your account
    - sn: device sn
- rate limit: Up to 50 times in 5 minutes
- response
```
{
    "code": 0,
    "msg": "",
    "data": {
        "height": 949715,
        "connected": 1,
        "dialable": 1,
        "natType": 2,
        "ipPublic": [
            "113.87.161.6"
        ],
        "ipEthLocal": [
            "192.168.177.6"
        ],
        "ipWifiLocal": [
            "0.0.0.0"
        ],
        "syncList": [
            {
                "height": 949715,
                "total": 955790,
                "time": 1628325601919
            },
            {
                "height": 949699,
                "total": 955786,
                "time": 1628325297832
            },
            {
                "height": 949680,
                "total": 955774,
                "time": 1628324990548
            },
            {
                "height": 949625,
                "total": 955758,
                "time": 1628324037462
            },
            {
                "height": 949500,
                "total": 955735,
                "time": 1628322481805
            },
            {
                "height": 949485,
                "total": 955719,
                "time": 1628322172950
            },
            {
                "height": 949460,
                "total": 955719,
                "time": 1628321868938
            },
            {
                "height": 949443,
                "total": 955719,
                "time": 1628321565039
            },
            {
                "height": 949430,
                "total": 955718,
                "time": 1628321259696
            },
            {
                "height": 949420,
                "total": 955713,
                "time": 1628320946924
            }
        ],
        "p2pAddress": [
            "/p2p/112WNiFan46rojvbsaWJKk1DGDS2oL2mP7b6vqBQ9WvAVNgrDzXg/p2p-circuit/p2p/11JdVNmGpfa9pnAAZVwMRJD5buZnCuPusCm2Po1n6ACTsB9kuc2"
        ],
        "fan_status_list": [],
        "blockStatus": -1,
        "relay": false,
        "labels": [],
        "bindUserArr": [
            "6110d47bc5e9994b17222896",
            "61148befd481e9379295e5ef"
        ],
        "sn": "110991585001000034",
        "address": "11JdVNmGp1a9pnAAZVwMRJD5buZnCuPusCm2Po1n6ACTsB9kuc2",
        "batch": "20210622-A",
        "collectTime": 1628325602020,
        "cpuId": "10000000f2f1248c",
        "cpuTemperature": 34,
        "cpuUsed": 52.3,
        "memoryTotal": 1900.79,
        "memoryUsed": 566.34,
        "name": "Brisk Bone Narwhal",
        "onboardingKey": "11JdVNmGp1a9pnAAZVwMRJD5buZnCuPusCm2Po1n6ACTsB9kuc2",
        "producedAt": 1624261107175,
        "sdTotal": 58776.86,
        "sdUsed": 1925.95,
        "version": {
            "firmware": "2021.08.02.1"
        },
        "wifiSsid": "",
        "addToHeliumAt": 1628056866000,
        "gain": 1.2,
        "totalHeight": 0,
        "synced": true,
        "online": false,
        "isHealth": 2,
        "relayed": 1
    }
}
```
- example request
```
curl --request GET \
     --url https://status.sensecapmx.cloud/api/openapi/device/view_device?sn=<your device sn>&api_key=<your apiKey>
```

## Device list
**Get the list of all devices**

- path: {host}/api/openapi/device/list_device
- method: GET
- params:
    - api_key: apikey of your account
- rate limit: Up to 2 times in 1 minutes
- response
```
{
    "code": 0,
    "msg": "",
    "data": {
        "page": {
            "count": 4
        },
        "list": [
            {
                "name": "Bumpy Lead Woodpecker",
                "sn": "110991585100000034",
                "cpuId": "100000006311af29",
                "batch": "20210707",
                "producedAt": 1625644529632,
                "addToHeliumAt": 1624007162000,
                "collectTime": 1631069266022,
                "version": {
                    "firmware": "2021.09.03.0"
                },
                "dialable": 1,
                "connected": 1,
                "relayed": 1,
                "gain": 1.2,
                "p2pAddress": [
                    "/p2p/11owsJ953YdSYCk7QqZcNepj93pgYKASp9AEhiVEqfaPBTYB8hj/p2p-circuit/p2p/112kUKYejYV9MssUxy2mXErMFT55xMcenaJ834oH3Umhk7caUBBm"
                ],
                "totalHeight": "0",
                "height": 1001599,
                "isHealth": 2,
                "natType": 2,
                "deviceOnline": false,
                "synced": true,
                "labels": [],
                "address": "112kUKYejYV9MssUxy21XErMFT55xMcenaJ834oH3Umhk7caUBBm",
                "owner": "133jU7Z49hcLZARp7CZpCBa1ZC214zoa3SKDMG52uv9H6wPMgLB"
            },
            ...
        ]
    }
}
```
- example request
```
curl --request GET \
     --url https://status.sensecapmx.cloud/api/openapi/device/list_device?api_key=<your apiKey>
```

## Error Code

code| msg | description
---|---|---
10000 | Framework analysis error | Service error
11100 | Invalid token | The apikey is Error
11200 | Request parameters are invalid | Request parameters are invalid
11203 | device no exists | this device is no exists
11207 | rate limit | The api is called too frequently
