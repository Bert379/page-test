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
        "height": 983142,
        "connected": 1,
        "dialable": 1,
        "natType": 1,
        "balenaVpnOnline": 0,
        "ipPublic": [
            "5.178.180.87"
        ],
        "ipEthLocal": [
            "192.168.5.117"
        ],
        "ipWifiLocal": [
            "0.0.0.0"
        ],
        "syncList": [
            {
                "height": 983142,
                "total": 989882,
                "time": 1630389677784
            },
            {
                "height": 983127,
                "total": 989878,
                "time": 1630389374727
            },
            {
                "height": 983111,
                "total": 989870,
                "time": 1630389071605
            },
            {
                "height": 983091,
                "total": 989868,
                "time": 1630388770447
            },
            {
                "height": 983075,
                "total": 989859,
                "time": 1630388468354
            },
            {
                "height": 983055,
                "total": 989856,
                "time": 1630388165049
            },
            {
                "height": 983034,
                "total": 989851,
                "time": 1630387860903
            },
            {
                "height": 983018,
                "total": 989847,
                "time": 1630387557924
            },
            {
                "height": 983000,
                "total": 989840,
                "time": 1630387254739
            },
            {
                "height": 982985,
                "total": 989835,
                "time": 1630386952607
            }
        ],
        "p2pAddress": [
            "/p2p/11AQ7eYYpx5S46ozLmEAbw8tYd9EudmEwWMH8QvcSS4FpbT8NvY/p2p-circuit/p2p/1123sJaktx8G73v36CkZmiHaHgaQ8u2doLB7NQBiRTedowkzHcDa"
        ],
        "fan_status_list": [
            {
                "fan": 0,
                "force": 0,
                "temperature": 37,
                "time": 1630337499821
            },
            {
                "fan": 1,
                "force": 0,
                "temperature": 38,
                "time": 1630337469819
            }
        ],
        "blockStatus": -1,
        "relay": false,
        "labels": [
            
        ],
        "sn": "110991613213000467",
        "batch": "20210721",
        "producedAt": 1626512107000,
        "uuid": "5e0e950848bb1f8b41db10dd3d783a08",
        "address": "112RJxpvdju1bz8wnBTebx9RaBn1LXTA22RamW7DH13d7bgUY3Yv",
        "collectTime": 1630389677861,
        "cpuId": "10000000c81bca52",
        "cpuTemperature": 45,
        "cpuUsed": 65.5,
        "memoryTotal": 1900.79,
        "memoryUsed": 653.58,
        "name": "Stale Coffee Opossum",
        "onboardingKey": "112RJxpvdju1bz8wnBTebx9RaBn1LXTA22RamW7DH13d7bgUY3Yv",
        "region": "unknown",
        "sdTotal": 58776.86,
        "sdUsed": 3226.68,
        "version": {
            "firmware": "2021.08.24.4"
        },
        "wifiSsid": "",
        "addToHeliumAt": 1630337148000,
        "gain": 1.2,
        "owner": "143LU8d123VK31djT2hEGapzfLGpntiXqTok4T5i8ugE23cGEoH",
        "totalHeight": 1003437,
        "synced": false,
        "online": false,
        "heliumOnline": false,
        "isHealth": 2,
        "relayed": -1
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
