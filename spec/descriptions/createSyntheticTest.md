This API endpoint creates a Synthetic Test.

**Note:** The **DNSAction** Synthetic type is not supported.

## Sample script and payload: 
- A sample script to create an API Simple test

```
curl -k -v -X POST \
https://<Host>/api/synthetics/settings/tests \
-H 'authorization: apiToken <Token>' \
-H 'content-type: application/json' \
-d '{
    "label":"Test_SimplePing",
    "description":"this is to test a simple ping API",
    "serviceId":"serviceId001",
    "applicationId":"applicationId001",
    "active":true,
    "testFrequency":1,
    "playbackMode":"Simultaneous",
    "locations":[
        "saas_instana_test"
    ],
    "configuration":{
        "syntheticType":"HTTPAction",
        "url":"https://httpbin.org/post",
        "operation":"POST",
        "headers":{
            "Content-Type":"text/plain"
        },
        "body":"Hello World!",
        "validationString":"Hello World!"
    },
    "customProperties":{
        "Team":"DevTeam",
        "Purpose":"Demo"
    }
  }'
```