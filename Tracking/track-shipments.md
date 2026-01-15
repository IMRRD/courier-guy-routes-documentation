# COURIER GUY – Track Shipments

- You need to be logged inside of session-server to be able to test.

## Endpoint
**GET**  
`http://192.168.110.164:8823/Tracking/TrackShipments?trackingReference={tracking_reference}`

## Purpose
Retrieves real-time tracking information and status updates for a shipment based on its tracking reference.
This endpoint is used to monitor shipment progress, view tracking events, and determine the current delivery stage.

---

## Path Parameter
| Parameter   | Description                      |
|---------    |----------------------------------|
| `tracking_reference` |  A unique identifier assigned to a shipment, used to track and retrieve shipment details throughout the delivery lifecycle, can be found on portal, inside shipment info |

📥 Response Example:


```json
{
    "shipments": [
        {
            "provider_id": 10,
            "shipment_id": 97389223,
            "short_tracking_reference": "FV4XVM",
            "status": "collection-assigned",
            "shipment_time_created": "2026-01-14T00:42:51.508297+00:00",
            "shipment_time_modified": "2026-01-14T00:42:51.884727+00:00",
            "shipment_collected_date": null,
            "shipment_delivered_date": null,
            "shipment_estimated_delivery_from": "2026-01-16T06:00:00+00:00",
            "shipment_estimated_delivery_to": "2026-01-19T15:00:00+00:00",
            "collection_from": "Shiplogic",
            "collection_hub": "Gauteng",
            "delivery_hub": "Gauteng",
            "service_level_code": "ECO",
            "service_level_name": "Economy",
            "parcel_count": 1,
            "tracking_events": [
                {
                    "id": 2129570191,
                    "parcel_id": 0,
                    "date": "2026-01-14T00:42:51.800913+00:00",
                    "status": "submitted",
                    "message": "",
                    "lat": null,
                    "lng": null,
                    "data": null,
                    "shipment_files": []
                }
            ]
        }
    ],
    "tracking_steps": [
        {
            "step_number": 1,
            "label": "created",
            "progress": "current"
        },
        {
            "step_number": 2,
            "label": "collected",
            "progress": "pending"
        },
        {
            "step_number": 3,
            "label": "in-transit",
            "progress": "pending"
        },
        {
            "step_number": 4,
            "label": "out-for-delivery",
            "progress": "pending"
        },
        {
            "step_number": 5,
            "label": "delivered",
            "progress": "pending"
        }
    ]
}
```

---


ℹ️ ⚠️ *Click the link below to learn more about the information related to this specific call (route).*

https://www.shiplogic.com/api-docs/get-tracking-a-shipment