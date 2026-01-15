# COURIER GUY – Get shipping Label Url

- You need to be logged inside of session-server to be able to test.

## Endpoint
**GET**  
`http://192.168.110.164:8823/Shipping/GetShipmentLabelUrl?id={id}`

## Purpose
Retrieves a secure, time-limited URL to download the shipping label (waybill) PDF for a specific shipment.
This endpoint is used to access and print shipment labels for operational and fulfillment purposes.

---

## Path Parameter
| Parameter   | Description                      |
|---------    |----------------------------------|
| `id` | Shipment Identifier  |


A valid shipment value: *97389223*

📥 Response Example:


```json
{
    "url": "https://shiplogic-backend-prod-infra-label-pdfs.s3.af-south-1.amazonaws.com/Label_10_FV4XVM.pdf?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIA55D5DNTBDOA3JW7Q%2F20260115%2Faf-south-1%2Fs3%2Faws4_request&X-Amz-Date=20260115T021857Z&X-Amz-Expires=604800&X-Amz-SignedHeaders=host&x-id=GetObject&X-Amz-Signature=10b01b6dc3a79d8df9b1aff157579c869edbd0f83f01ea8ad5d150b271a4fa31",
    "filename": "Label_10_FV4XVM.pdf",
    "bucket": "shiplogic-backend-prod-infra-label-pdfs",
    "file_size": 30631,
    "expiry_duration": "7 days"
}
```

---


ℹ️ ⚠️ *Click the link below to learn more about the information related to this specific call (route).*

https://www.shiplogic.com/api-docs/get-getting-shipment-label-%2F-waybill-pdf