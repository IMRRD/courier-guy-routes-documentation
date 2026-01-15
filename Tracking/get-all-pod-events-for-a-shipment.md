# COURIER GUY – Get All Pod Events For A Shipment

- You need to be logged inside of session-server to be able to test.

## Endpoint
**GET**  
`http://192.168.110.164:8823/Tracking/GetAllPodEventsForAShipment?trackingReference={tracking_reference}&includeDigitalPod=true`

## Purpose
Retrieves all Proof of Delivery (POD) events associated with a specific shipment, with optional inclusion of digital POD details.
This endpoint is used to review the full delivery confirmation history and validate POD-related events for tracking and auditing purposes.

---

## Path Parameter
| Parameter   | Description                      |
|---------    |----------------------------------|
| `tracking_reference` |  A unique identifier assigned to a shipment, used to track and retrieve shipment details throughout the delivery lifecycle, can be found on portal, inside shipment info |
| `includeDigitalPod` | identifier that indicates whether the response should include the digital Proof of Delivery (Digital POD) data. When set to true, the response will include available digital POD details such as recipient confirmation, signatures, or related metadata.|

📥 Response Example:

❌ No response example is currently available for this endpoint with our info on platform yet or have to find out a valid value

204 - No Content

---


ℹ️ ⚠️ *Click the link below to learn more about the information related to this specific call (route).*

https://www.shiplogic.com/api-docs/get-getting-all-pod-events-for-a-shipment