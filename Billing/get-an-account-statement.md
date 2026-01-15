# COURIER GUY – Get an Account Statement

- You need to be logged inside of session-server to be able to test.

## Endpoint
**GET**  
`http://192.168.110.164:8823/Billing/GetAnAccountStatement?start_date={start_date}&end_date={end_date}&pdf=true`

## Purpose
Retrieves an account statement for the specified date range and, when requested, returns a secure URL to download the statement in PDF format or details.
The statement is generated on demand based on existing billing data for reporting and reconciliation purposes.

---

## Path Parameter
| Parameter   | Description                      |
|---------    |----------------------------------|
| `start_date` | Start date of the period to be considered when generating the account statement. |
| `end_date` | End date of the period to be considered when generating the account statement. |
| `pdf`  | Identifier to return the pdf path or false for the info |

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
 ❌ NOT IMPLEMENTED ENTIRELY YET
```

---


ℹ️ ⚠️ *Click the link below to learn more about the information related to this specific call (route).*

https://www.shiplogic.com/api-docs/get-getting-an-account-statement