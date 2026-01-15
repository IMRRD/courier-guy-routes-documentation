Valid id value: 97389223

# COURIER GUY – Get Shipping Sticker Label Url

- You need to be logged inside of session-server to be able to test.

## Endpoint
**GET**  
`http://192.168.110.164:8823/Shipping/GetShipmentStickerLabelUrl?id={id}`

## Purpose
Retrieves a secure, time-limited URL to download the shipping sticker label PDF for a specific shipment.
This endpoint is used to access and print shipment stickers for packaging, identification, and handling during fulfillment.

---

## Path Parameter
| Parameter   | Description                      |
|---------    |----------------------------------|
| `id` | Shipment Identifier  |

A valid shipment value: *97389223*

📥 Response Example:


```json
{
    "url": "https://shiplogic-backend-prod-infra-label-pdfs.s3.af-south-1.amazonaws.com/Stickers_10_FV4XVM.pdf?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIA55D5DNTBDOA3JW7Q%2F20260115%2Faf-south-1%2Fs3%2Faws4_request&X-Amz-Date=20260115T022033Z&X-Amz-Expires=604800&X-Amz-SignedHeaders=host&x-id=GetObject&X-Amz-Signature=a0aa39dfe6467d811f025fd60a13256625bf5ed68550fea461b2ae1f219b6c80",
    "filename": "Stickers_10_FV4XVM.pdf",
    "bucket": "shiplogic-backend-prod-infra-label-pdfs",
    "file_size": 22481,
    "expiry_duration": "7 days"
}
```

---


ℹ️ ⚠️ *Click the link below to learn more about the information related to this specific call (route).*

https://www.shiplogic.com/api-docs/get-getting-shipment-sticker-label