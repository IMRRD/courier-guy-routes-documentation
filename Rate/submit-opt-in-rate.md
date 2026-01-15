# COURIER GUY – Submit Opt In Rate

- You need to be logged inside of session-server to be able to test.

## Endpoint
**POST**  
`http://192.168.110.164:8823/Rate/SubmitOptInRate`

## Purpose
Submits collection and delivery address details to retrieve available opt-in and time-based rates applicable to the shipment.
This endpoint is used to identify optional services and additional charges that can be applied before shipment creation.

---


## Request Body Example

- The pageSize filter is working even on dev, it's dynamic, if you send 1 is gonna return 1 record...

```json
{
     "collection_address": {
        "type": "business",
        "company": "Shiplogic",
        "street_address": "194 Bancor Avenue",
        "local_area": "Menlyn",
        "city": "Pretoria",
        "zone": "Gauteng",
        "country": "ZA",
        "code": "0181"
    },
    "delivery_address": {
        "type": "residential",
        "company": "",
        "street_address": "10 Midas Avenue",
        "local_area": "Olympus AH",
        "city": "Pretoria",
        "zone": "Gauteng",
        "country": "ZA",
        "code": "0081",
        "lat": -25.80665579999999,
        "lng": 28.334732
    }
}
```

📥 Response Example:

```json
{
    "opt_in_rates": [
        {
            "id": 467883,
            "name": "Gift wrapping",
            "charge_type": "flat",
            "charge_value": 50,
            "description": "",
            "opted_in_by_default": false
        }
    ],
    "opt_in_time_based_rates": [
        {
            "id": 663699,
            "name": "Saturday delivery",
            "charge_type": "flat",
            "charge_value": 200,
            "description": "",
            "opted_in_by_default": false
        }
    ],
    "count": 1
}
```

---


ℹ️ ⚠️ *Click the link below to learn more about the information related to this specific call (route).*

https://www.shiplogic.com/api-docs/post-getting-opt-in-rates