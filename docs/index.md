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
        "height": 1003444,
        "connected": 1,
        "dialable": 1,
        "natType": 2,
        "ipPublic": [
            "113.110.229.80"
        ],
        "ipEthLocal": [
            "192.168.88.119"
        ],
        "ipWifiLocal": [
            "0.0.0.0"
        ],
        "syncList": [
            {
                "height": 1003424,
                "total": 1003427,
                "time": 1631180053960
            },
            {
                "height": 1003419,
                "total": 1003422,
                "time": 1631179746009
            },
            {
                "height": 1003416,
                "total": 1003416,
                "time": 1631179440140
            },
            {
                "height": 1003408,
                "total": 1003409,
                "time": 1631179128392
            },
            {
                "height": 1003393,
                "total": 1003399,
                "time": 1631178100688
            },
            {
                "height": 1003387,
                "total": 1003393,
                "time": 1631177794943
            },
            {
                "height": 1003384,
                "total": 1003387,
                "time": 1631177452093
            },
            {
                "height": 1003376,
                "total": 1003382,
                "time": 1631177145336
            },
            {
                "height": 1003376,
                "total": 1003377,
                "time": 1631176839656
            },
            {
                "height": 1003372,
                "total": 1003372,
                "time": 1631176533018
            }
        ],
        "p2pAddress": [
            "/p2p/11LmGup58X4UXTajwmsYZhuXVcNYvnBCf4UGM3jx282iMotBR7j/p2p-circuit/p2p/112kS4A6sgZCTHU7gHyK1nBVhWVUMj2mSN11uARCEcREAd3WSj74"
        ],
        "fan_status_list": [
            {
                "fan": 1,
                "force": 0,
                "temperature": 72,
                "time": 1631181015278
            },
            {
                "fan": 1,
                "force": 0,
                "temperature": 71,
                "time": 1631180925273
            },
            {
                "fan": 1,
                "force": 0,
                "temperature": 70,
                "time": 1631180835269
            },
            {
                "fan": 1,
                "force": 0,
                "temperature": 72,
                "time": 1631180805267
            },
            {
                "fan": 1,
                "force": 0,
                "temperature": 70,
                "time": 1631180775265
            },
            {
                "fan": 1,
                "force": 0,
                "temperature": 72,
                "time": 1631180745263
            },
            {
                "fan": 1,
                "force": 0,
                "temperature": 72,
                "time": 1631180715262
            },
            {
                "fan": 1,
                "force": 0,
                "temperature": 70,
                "time": 1631180655259
            },
            {
                "fan": 1,
                "force": 0,
                "temperature": 71,
                "time": 1631180625257
            },
            {
                "fan": 1,
                "force": 0,
                "temperature": 71,
                "time": 1631180595256
            }
        ],
        "blockStatus": 1,
        "relay": false,
        "labels": [],
        "sn": "110991321213002033",
        "address": "112kS4A6sg1CTHU7gHyK1nBVhWVUMj2mSN11uARCEcREAd3WSj74",
        "batch": null,
        "collectTime": 1631181103754,
        "cpuId": "100000002be60194",
        "cpuTemperature": 67,
        "cpuUsed": 37.6,
        "memoryTotal": 1900.79,
        "memoryUsed": 690.07,
        "name": "Fantastic Pecan Robin",
        "onboardingKey": "112kS4A6sg1CTHU7gHyK1nBVhWVUMj2mSN11uARCEcREAd3WSj74",
        "producedAt": 1625707693512,
        "region": "US915",
        "sdTotal": 58776.86,
        "sdUsed": 30533.79,
        "version": {
            "firmware": "2021.09.03.0"
        },
        "wifiSsid": "",
        "addToHeliumAt": 1624003515000,
        "gain": 1.2,
        "owner": "133jU7Z49hcLZARp1CZpCBa1ZC234zoa3SKDMG52uv9H6wPMgLB",
        "geocode": {
            "short_street": "Irish-American Dam Rd",
            "short_state": "NV",
            "short_country": "US",
            "short_city": "Lovelock",
            "long_street": "Irish-American Dam Road",
            "long_state": "Nevada",
            "long_country": "United States",
            "long_city": "Lovelock",
            "city_id": "bG92ZWxvY2tuZXZhZGF1bml0ZWQgc3RhdGVz"
        },
        "heliumOnline": true,
        "lat": 40.21757423872224,
        "lng": -118.42763826806683,
        "totalHeight": 1003445,
        "synced": true,
        "online": true,
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
