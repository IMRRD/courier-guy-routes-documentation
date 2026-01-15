# COURIER GUY – Get Items For Credit Note

- You need to be logged inside of session-server to be able to test.

## Endpoint
**GET**  
`http://192.168.110.164:8823/Billing/GetItemsForCreditNote?credit_note_id={credit_note_id}`

## Purpose
Retrieves the list of items associated with a specific credit note.
This endpoint is used to inspect credit note details and understand the individual adjustments applied to billing records.

---

## Path Parameter
| Parameter   | Description                      |
|---------    |----------------------------------|
| `credit_note_id` | Credit Note Identifier  |

📥 Response Example:

❌ No response example is currently available for this endpoint with our info on platform yet or have to find out a valid value

```json
{
    "credit_note_items": [],
    "count": 0
}
```

---


ℹ️ ⚠️ *Click the link below to learn more about the information related to this specific call (route).*

https://www.shiplogic.com/api-docs/get-getting-items-for-credit-note