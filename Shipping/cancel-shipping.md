# COURIER GUY – Cancel Shipment

- You need to be logged inside of session-server to be able to test.

## Endpoint
**POST**  
`http://192.168.110.164:8823/Shipping/CancelShipment`

## Purpose
Cancels an existing shipment identified by its tracking reference.
This endpoint updates the shipment status to cancelled and returns the updated shipment details for confirmation and auditing purposes.

---


## Request Body Example

- The pageSize filter is working even on dev, it's dynamic, if you send 1 is gonna return 1 record...

```json
{
  "tracking_reference": "invalid"
}
```

📥 Response Example:



```json
{
    "id": 97389221,
    "provider_id": 10,
    "provider": {
        "name": null,
        "time_created": null,
        "invoice_counter": 0,
        "credit_note_counter": 0,
        "interhub_transfer_counter": 0,
        "hik_vision_last_tracking_event_id": 0
    },
    "account_id": 616353,
    "account": {
        "id": 616353,
        "provider_id": 10,
        "branch_id": 2948,
        "branch_name": null,
        "name": "IALogics",
        "account_code": "IAL001",
        "account_type": "postpaid",
        "credit_limit": 10000000,
        "payment_terms": 30,
        "invoice_frequency": "monthly",
        "invoice_frequency_time": 0,
        "balance": -1500,
        "credit_allocation_balance": 0,
        "is_on_hold": false,
        "disable_auto_hold": false,
        "temp_disable_auto_hold": false,
        "charge_discrepancy_threshold_override": 0,
        "invoice_allocation_method": "auto-oldest-invoice-first",
        "created_by": "almadavic-268989",
        "time_created": "2025-12-17T17:19:37.009576Z",
        "time_modified": "2025-12-17T17:19:37.126239Z",
        "default_collection_address_id": 24074850,
        "custom_fields": null,
        "cost_centers": null,
        "force_show_billing_transactions": false,
        "invoice_trigger_shipment_status": null,
        "invoice_trigger_shipment_status_for_month_end": null,
        "status": "open",
        "trading_start_date": null,
        "current_rate_group_id": 148799,
        "current_rate_group_name": "Default group",
        "pod_method": "pin-with-fallback",
        "pod_method_visible_on_shipment": false,
        "include_unencrypted_pod_pin": false,
        "disable_out_for_delivery_sms": false,
        "disable_out_for_delivery_email": false,
        "disable_driver_app_notification_sms": false,
        "disable_driver_app_notification_email": false,
        "disable_account_in_arrears_checks": false,
        "override_tracking_prefixes": false,
        "allow_cancelling_failed_collections": false,
        "referrer": "https://chatgpt.com/"
    },
    "short_tracking_reference": "NW3TCM",
    "customer_reference": "ORDERNO123",
    "latest_tracking_event_time": "2026-01-15T02:28:46.442662Z",
    "time_created": "2026-01-14T00:42:16.660813Z",
    "time_modified": "2026-01-15T02:28:46.550949Z",
    "modified_by": "almadavic-26898973281cb8-7759-49d8-80fe-6cfeb887ed41",
    "created_by": "almadavic-26898973281cb8-7759-49d8-80fe-6cfeb887ed41",
    "deleted_date": "0001-01-01T00:00:00Z",
    "source": "api",
    "collection_min_date": "2026-01-13T22:00:00Z",
    "collection_after": "08:00",
    "collection_before": "16:00",
    "delivery_min_date": "2026-01-13T22:00:00Z",
    "delivery_after": "10:00",
    "delivery_before": "17:00",
    "collection_request_id": 0,
    "status": "cancelled",
    "delivery_agent_id": "sandydriver",
    "collection_agent_id": "sandydriver",
    "original_delivery_agent_id": "sandydriver",
    "original_collection_agent_id": "sandydriver",
    "collection_agent_zone": "Gauteng",
    "collection_agent_routing_number": "JNB-J1",
    "delivery_agent_zone": "Gauteng",
    "delivery_agent_routing_number": "JNB-J1",
    "delivery_read_by_driver_time": null,
    "collection_read_by_driver_time": null,
    "collection_address_id": 74327890,
    "collection_address": {
        "id": 74327890,
        "gs_hash": "5A9E1884E199FB63429FAED624862DD1",
        "time_modified": "2025-08-01T12:28:35.557146Z",
        "hash": "795FCEBB4DD7E20F3C36AB01A42D8E9E",
        "entered_address": "Shiplogic, 194 Bancor Avenue, Menlyn, Pretoria, 0181, GP, South Africa",
        "company": "Shiplogic",
        "street_address": "194 Bancor Avenue",
        "local_area": "Menlyn",
        "code": "0181",
        "city": "Pretoria",
        "zone": "GP",
        "country": "South Africa",
        "lat": -25.786642,
        "lng": 28.282176,
        "geo_local_area": "Menlyn",
        "geo_city": "City of Tshwane Metropolitan Municipality",
        "time_created": "2025-08-01T12:28:35.557146Z",
        "type": "business"
    },
    "collection_address_book_id": 0,
    "collection_pickup_point_provider": null,
    "collection_contact": {
        "provider_id": 10,
        "shipment_id": 0,
        "name": "Cornel Rautenbach",
        "mobile_number": "",
        "email": "cornel+sandy@shiplogic.com"
    },
    "delivery_address_id": 85241759,
    "delivery_address": {
        "id": 85241759,
        "gs_hash": null,
        "time_modified": "2026-01-14T00:42:16.687677Z",
        "hash": "3926075BCEF37DD2CBBE6CA939F1295C",
        "entered_address": "10 Midas Ave, Olympus AH, Pretoria, 0081, GP, South Africa",
        "street_address": "10 Midas Ave",
        "local_area": "Olympus AH",
        "code": "0081",
        "city": "Pretoria",
        "zone": "GP",
        "country": "South Africa",
        "lat": -25.806656,
        "lng": 28.334732,
        "time_created": "2026-01-14T00:42:16.687677Z",
        "type": "residential"
    },
    "delivery_address_book_id": 0,
    "delivery_pickup_point_provider": null,
    "delivery_contact": {
        "provider_id": 10,
        "shipment_id": 0,
        "name": "",
        "mobile_number": "",
        "email": "james+sandyreceiver@shiplogic.com"
    },
    "parcels": [
        {
            "id": 112677123,
            "provider_id": 10,
            "status": "cancelled",
            "tracking_reference": "NW3TCM/1",
            "packaging": "Custom parcel",
            "shipment_id": 97389221,
            "shipment": null,
            "submitted_length_cm": 20,
            "submitted_width_cm": 20,
            "submitted_height_cm": 10,
            "submitted_weight_kg": 2,
            "actual_length_cm": 20,
            "actual_width_cm": 20,
            "actual_height_cm": 10,
            "actual_weight_kg": 2,
            "has_been_dimensioned": false,
            "time_created": "2026-01-14T00:42:16.687677Z",
            "time_modified": "2026-01-15T02:28:46.401236Z"
        }
    ],
    "service_level_code": "ECO",
    "service_level_name": "Economy",
    "service_level_id": 139841,
    "original_shipment_information": {
        "original_service_level_code": "ECO",
        "original_service_level_name": "Economy"
    },
    "rate": 120,
    "original_rate": 120,
    "previous_rate": 0,
    "charged_weight": 2,
    "actual_weight": 2,
    "volumetric_weight": 1,
    "declared_value": 1100,
    "rates": [
        {
            "id": 364236559,
            "provider_id": 10,
            "shipment_id": 97389221,
            "rate_revision_id": 22599,
            "name": "",
            "type": "base",
            "type_id": 148799,
            "value": 95,
            "vat": 12.3913,
            "vat_percentage": null,
            "vat_type": "standard",
            "valid_from": "2026-01-14T00:42:16.91122Z",
            "valid_until": null,
            "is_opt_in": false,
            "is_custom_charge": false,
            "is_quantity_based_charge": false,
            "quantity": 0,
            "metadata": {
                "shipment_tracking_reference": "NW3TCM",
                "service_level_code": "ECO",
                "parcels": [
                    {
                        "id": 112677123,
                        "provider_id": 10,
                        "status": "collection-assigned",
                        "tracking_reference": "NW3TCM/1",
                        "packaging": "Custom parcel",
                        "shipment_id": 97389221,
                        "shipment": null,
                        "submitted_length_cm": 20,
                        "submitted_width_cm": 20,
                        "submitted_height_cm": 10,
                        "submitted_weight_kg": 2,
                        "actual_length_cm": 20,
                        "actual_width_cm": 20,
                        "actual_height_cm": 10,
                        "actual_weight_kg": 2,
                        "has_been_dimensioned": false,
                        "time_created": "2026-01-14T00:42:16.687677Z"
                    }
                ],
                "charged_weight": 2,
                "estimated_weight": 2,
                "shipment_id": 97389221
            },
            "billing_transaction_id": 101928839
        },
        {
            "id": 364236560,
            "provider_id": 10,
            "shipment_id": 97389221,
            "rate_revision_id": 22599,
            "name": "",
            "type": "rate_formula",
            "type_id": 5463716,
            "value": 95,
            "vat": 12.3913,
            "vat_percentage": 15,
            "vat_type": "standard",
            "valid_from": "2026-01-14T00:42:16.91122Z",
            "valid_until": null,
            "is_opt_in": false,
            "is_custom_charge": false,
            "is_quantity_based_charge": false,
            "quantity": 0,
            "metadata": null,
            "billing_transaction_id": 101928839
        },
        {
            "id": 364236561,
            "provider_id": 10,
            "shipment_id": 97389221,
            "rate_revision_id": 22599,
            "name": "",
            "type": "rate_group_extras",
            "type_id": 148342,
            "value": 25,
            "vat": 3.2609,
            "vat_percentage": null,
            "vat_type": "standard",
            "valid_from": "2026-01-14T00:42:16.91122Z",
            "valid_until": null,
            "is_opt_in": false,
            "is_custom_charge": false,
            "is_quantity_based_charge": false,
            "quantity": 0,
            "metadata": null,
            "billing_transaction_id": 101928839
        }
    ],
    "special_instructions_collection": "This is a test shipment - DO NOT COLLECT",
    "special_instructions_delivery": "This is a test shipment - DO NOT DELIVER",
    "proof_of_delivery_pin_hashed": "EiqVpjkbdVziQJCnmdRYHErFOqn/h/HMbA8fs0iIWR4=",
    "collected_date": null,
    "original_collected_date": null,
    "delivered_date": null,
    "is_return": false,
    "estimated_collection": "2026-01-14T06:00:00Z",
    "original_estimated_collection": "2026-01-14T06:00:00Z",
    "estimated_delivery_from": "2026-01-16T06:00:00Z",
    "estimated_delivery_to": "2026-01-19T15:00:00Z",
    "original_estimated_delivery_from": "2026-01-16T06:00:00Z",
    "earliest_collection_capacity_date": null,
    "is_pending": false,
    "current_branch_id": 272,
    "current_branch_name": "Gauteng",
    "current_branch_public_name": "",
    "collection_branch_id": 272,
    "collection_branch_name": "Gauteng",
    "collection_branch_public_name": "",
    "delivery_branch_id": 272,
    "delivery_branch_name": "Gauteng",
    "delivery_branch_public_name": "",
    "account_branch_id": 2948,
    "transient_branch_ids": null,
    "service_level_cut_off_time": "2026-01-14T13:00:00Z",
    "collection_cutoff_override": false,
    "total_note_count": 0,
    "external_note_count": 0,
    "requires_action_note_count": 0,
    "disable_new_charges": false,
    "mute_notifications": false,
    "payment_intervention_status": "",
    "pod_method": "pin-with-fallback",
    "has_pod_files": false,
    "all_pods_are_verified": null,
    "has_been_invoiced": false,
    "tracking_events": null,
    "collection_rescheduled": false,
    "delivery_rescheduled": false,
    "rating_reference": "fb070210-9eab-429f-9dd2-046a5284da2f",
    "has_rating": false,
    "payment_reference": "b366c177-ddab-4d8c-aedc-5ffc16b6dc45",
    "submitted_date": "2026-01-14T00:42:16.973558Z",
    "priority_level": 0
}
```

---



ℹ️ ⚠️ *Click the link below to learn more about the information related to this specific call (route).*

https://www.shiplogic.com/api-docs/post-cancelling-a-shipment