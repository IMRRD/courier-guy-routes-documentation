# COURIER GUY – Get shipping Notes

- You need to be logged inside of session-server to be able to test.

## Endpoint
**GET**  
`http://192.168.110.164:8823/Shipping/GetNotes/{id}`

## Purpose
Retrieves notes associated with a specific shipment.
This endpoint is used to review operational, system, or user-added notes linked to the shipment for tracking and auditing purposes.

---

## Path Parameter
| Parameter   | Description                      |
|---------    |----------------------------------|
| `id` |  ShipmentIdentifier |


📥 Response Example:

❌ No response example is currently available for this endpoint with our info on platform yet or have to find out a valid value

```json
{
    "shipment_notes": null,
    "count": 0
}
```

---


ℹ️ ⚠️ *Click the link below to learn more about the information related to this specific call (route).*

