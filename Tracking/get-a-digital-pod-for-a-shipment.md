# COURIER GUY – Get a Digital Pod for a Shipment

- You need to be logged inside of session-server to be able to test.

## Endpoint
**GET**  
`http://192.168.110.164:8823/Tracking/GetADigitalPodForAShipmnent?trackingReference={tracking_reference}`

## Purpose
Retrieves the digital Proof of Delivery (POD) associated with a shipment, when the shipment has been successfully delivered.
This endpoint is used to validate delivery completion and access POD records for auditing and customer confirmation.

---

## Path Parameter
| Parameter   | Description                      |
|---------    |----------------------------------|
| `tracking_reference` |  A unique identifier assigned to a shipment, used to track and retrieve shipment details throughout the delivery lifecycle, can be found on portal, inside shipment info |

📥 Response Example:

❌ No response example is currently available for this endpoint with our info on platform yet or have to find out a valid value

```json
System.Exception: Error to get shippment shipment not delivered
```

---


ℹ️ ⚠️ *Click the link below to learn more about the information related to this specific call (route).*

https://www.shiplogic.com/api-docs/get-getting-a-digital-pod-for-a-shipment