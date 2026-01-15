# COURIER GUY – 

- You need to be logged inside of session-server to be able to test.

## Endpoint
**GET**  
`http://192.168.110.164:8823/Billing/GetBillingTransactionsForAccount?order_by={order_by}&order={order}&limit={limit}&offset={offset}` // ARRUMAR COM {} ao inves de statico

## Purpose


---

## Path Parameter
| Parameter   | Description                      |
|---------    |----------------------------------|
| `` |  |

📥 Response Example:

- Returns just a single invoice

```json
{
    "transactions": [
        {
            "id": 99672305,
            "provider_id": 10,
            "transaction_date": "2025-12-18T02:16:32.597496Z",
            "effective_date": "2025-12-18T02:16:32.597496Z",
            "type": "shipping-charge",
            "sub_type": "",
            "payment_id": null,
            "description": null,
            "internal_note": null,
            "amount": -95,
            "vat": 12.3913,
            "vat_percentage": 15,
            "ex_vat_zero_rated": 0,
            "doc_display_id": null,
            "has_been_reversed": false,
            "shipment_id": 95161085,
            "shipment_reference": "PJ7GFF",
            "account_id": 616353,
            "account_code": "IAL001",
            "invoice_id": 0,
            "invoiceable": false,
            "imported_payment_id": 0,
            "credit_note_id": 0,
            "credit_note": null,
            "source": "api",
            "time_created": "2025-12-18T02:16:32.60345Z",
            "time_modified": "2025-12-18T02:16:32.603728Z",
            "modified_by": "almadavic-26898973281cb8-7759-49d8-80fe-6cfeb887ed41"
        }
    ],
    "count": 13
}
```

---


ℹ️ ⚠️ *Click the link below to learn more about the information related to this specific call (route).*

https://www.shiplogic.com/api-docs/get-getting-billing-transactions-for-account