# COURIER GUY – 

- You need to be logged inside of session-server to be able to test.

## Endpoint
**GET**  
`http://192.168.110.164:8823/Billing/GetAnAccountStatement?start_date={start_date}&end_date={end_date}&pdf=true`

## Purpose


---

## Path Parameter
| Parameter   | Description                      |
|---------    |----------------------------------|
| `` |  |

📥 Response Example:

-- If pdf parameter on url is true, it returns:

```json
{
  "url": "https://shiplogic-backend-prod-infra-billing-pdfs.s3.af-south-1.amazonaws.com/statement_10_616353_2025-11-01_2026-11-01.pdf?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIA55D5DNTBDOA3JW7Q%2F20260114%2Faf-south-1%2Fs3%2Faws4_request&X-Amz-Date=20260114T233040Z&X-Amz-Expires=604800&X-Amz-SignedHeaders=host&x-id=GetObject&X-Amz-Signature=fe0d59f971c0eaa35cb49896ff1e13e4635f835d16e2e339926df8706cfd341d",
  "filename": "statement_10_616353_2025-11-01_2026-11-01.pdf",
  "bucket": "shiplogic-backend-prod-infra-billing-pdfs",
  "file_size": 15931,
  "expiry_duration": "7 days"
}
```

-- If pdf parameter on url is false, it returns:

```json
```

---


ℹ️ ⚠️ *Click the link below to learn more about the information related to this specific call (route).*

https://www.shiplogic.com/api-docs/get-getting-an-account-statement