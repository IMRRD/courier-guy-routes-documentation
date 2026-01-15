# COURIER GUY – Get Items for Invoice

- You need to be logged inside of session-server to be able to test.

## Endpoint
**GET**  
`http://192.168.110.164:8823/Billing/GetItemsForInvoice?invoice_id={invoice_id}&order_by={order_by}&order={order}`

## Purpose
Retrieves the list of items associated with a specific invoice, with optional sorting of the results.
This endpoint is used to review invoice details and analyze the individual billing charges linked to an invoice.

---

## Path Parameter
| Parameter   | Description                      |
|---------    |----------------------------------|
| `invoice_id` | Invoice Identifier |
| `order_by` | Field used to sort the billing transactions (e.g., transaction_date) |
| `order` |  Sort direction. Accepted values are asc (ascending) or desc (descending). |

📥 Response Example:

❌ No response example is currently available for this endpoint with our info on platform yet or have to find out a valid value

```json
System.Exception: Error to get shippment failed to get invoice items, because failed to find invoice with ID
```

---


ℹ️ ⚠️ *Click the link below to learn more about the information related to this specific call (route).*

https://www.shiplogic.com/api-docs/get-getting-items-for-invoice