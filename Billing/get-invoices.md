# COURIER GUY – Get Invoices

- You need to be logged inside of session-server to be able to test.

## Endpoint
**GET**  
`http://192.168.110.164:8823/Billing/GetInvoices?start_date={start_date}&end_date={end_date}`

## Purpose
Retrieves invoices issued within the specified date range for the account.
This endpoint is intended for invoice review, financial reporting, and account reconciliation based on existing billing data.

---

## Path Parameter
| Parameter   | Description                      |
|---------    |----------------------------------|
| `start_date` | Start date of the period to be considered when generating the account statement. |
| `end_date` | End date of the period to be considered when generating the account statement. |

📥 Response Example:

❌ No response example is currently available for this endpoint with our info on platform yet or have to find out a valid value

```json
{
    "invoices": [],
    "count": 0
}
```

---


ℹ️ ⚠️ *Click the link below to learn more about the information related to this specific call (route).*

https://www.shiplogic.com/api-docs/get-getting-invoices