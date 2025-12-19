# Shipping API – Create Shipment

## Endpoint
POST /shipments

## Purpose
This endpoint is used to create a shipment in the logistics system. A shipment represents a confirmed delivery request and includes collection details, delivery details, parcel information, and the selected service level.

Once a shipment is successfully created, it becomes a persistent entity in the system and can be tracked, managed, and viewed in the logistics portal.

This endpoint is used after rates have been calculated and a service option has been selected.

## Typical Use Cases
This endpoint is typically used to create a confirmed shipment after a customer selects a shipping option, to schedule collections and deliveries, to generate trackable shipment records, and to persist delivery data for operational and reporting purposes.

## Request Overview
The request represents a confirmed shipment and includes the logistics provider, collection and delivery addresses, parcel details, and the selected service level obtained from a prior rate calculation.

Unlike rate requests, shipment creation persists data and triggers operational workflows such as collection scheduling and delivery processing.

## Request Example

```json

{
    "collection_address": {
        "type": "business",
        "company": "Shiplogic",
        "street_address": "194 Bancor Avenue",
        "local_area": "Menlyn",
        "city": "Pretoria",
        "zone": "Gauteng",
        "country": "ZA",
        "code": "0181"
    },
    "collection_contact": {
        "name": "Cornel Rautenbach",
        "mobile_number": "",
        "email": "cornel+sandy@shiplogic.com"
    },
    "delivery_address": {
        "type": "residential",
        "company": "",
        "street_address": "10 Midas Ave",
        "local_area": "Olympus AH",
        "city": "Pretoria",
        "code": "0081",
        "zone": "Gauteng",
        "country": "ZA",
        "lat": -25.80665579999999,
        "lng": 28.334732
    },
    "delivery_contact": {
        "name": "",
        "mobile_number": "",
        "email": "james+sandyreceiver@shiplogic.com"
    },
    "parcels": [
        {
            "parcel_description": "Standard flyer",
            "submitted_length_cm": 20,
            "submitted_width_cm": 20,
            "submitted_height_cm": 10,
            "submitted_weight_kg": 2
        }
    ],
    "opt_in_rates": [],
    "opt_in_time_based_rates": [
        76
    ],
    "special_instructions_collection": "This is a test shipment - DO NOT COLLECT",
    "special_instructions_delivery": "This is a test shipment - DO NOT DELIVER",
    "declared_value": 1100,
    "collection_min_date": "2021-05-21T00:00:00.000Z",
    "collection_after": "08:00",
    "collection_before": "16:00",
    "delivery_min_date": "2021-05-21T00:00:00.000Z",
    "delivery_after": "10:00",
    "delivery_before": "17:00",
    "custom_tracking_reference": "",
    "customer_reference": "ORDERNO123",
    "service_level_code": "ECO",
    "mute_notifications": false
}

```

## Shipment Creation Behavior
When a shipment is created:
- The shipment is stored in the system
- A shipment identifier is generated
- The shipment becomes visible in the logistics portal
- Operational processes such as collection and delivery can be initiated

This endpoint creates a real shipment, not a quotation.

## Response Overview
A successful response returns confirmation that the shipment was created along with shipment identifiers and status information. These identifiers can be used for tracking, updates, and support queries.

## Response Example

```json

{
  "id": 95464038,
  "provider_id": 10,
  "account_id": 616353,
  "short_tracking_reference": "PZDRMT",
  "latest_tracking_event_time": "2025-12-19T22:52:15.613927Z",
  "time_created": "2025-12-19T22:52:15.202041Z",
  "time_modified": "2025-12-19T22:52:15.681986Z",
  "created_by": "almadavic-26898973281cb8-7759-49d8-80fe-6cfeb887ed41",
  "modified_by": "almadavic-26898973281cb8-7759-49d8-80fe-6cfeb887ed41",
  "deleted_date": "0001-01-01T00:00:00Z",
  "source": "api",
  "collection_min_date": "2025-12-19T22:00:00Z",
  "collection_after": "08:00",
  "collection_before": "16:00",
  "delivery_min_date": "2025-12-19T22:00:00Z",
  "delivery_after": "10:00",
  "delivery_before": "17:00",
  "collection_request_id": 0,
  "status": "collection-assigned",
  "collection_agent_id": "sandydriver",
  "delivery_agent_id": "sandydriver",
  "collection_agent_zone": "Gauteng",
  "original_delivery_agent_id": "sandydriver",
  "original_collection_agent_id": "sandydriver",
  "delivery_agent_zone": "Gauteng",
  "collection_agent_routing_number": "JNB-J1",
  "delivery_agent_routing_number": "JNB-J1",
  "delivery_read_by_driver_time": null,
  "collection_read_by_driver_time": null,
  "delivery_pickup_point_provider": null,
  "collection_address_id": 74327890,
  "delivery_address_book_id": 0,
  "delivery_address_id": 84087200,
  "service_level_code": "ECO",
  "service_level_name": "Economy",
  "service_level_id": 139841,
  "rate": 120,
  "original_rate": 120,
  "previous_rate": 0,
  "charged_weight": 2,
  "actual_weight": 2,
  "volumetric_weight": 1,
  "declared_value": 1100,
  "is_return": false,
  "is_pending": false,
  "has_been_invoiced": false,
  "proof_of_delivery_pin_hashed": "PfgnDpmPYApQCePbhmO2LPsZXyjyRLLCqf2KclVu8EU=",
  "collected_date": null,
  "original_collected_date": null,
  "delivered_date": null,
  "estimated_collection": "2025-12-22T06:00:00Z",
  "original_estimated_collection": "2025-12-22T06:00:00Z",
  "estimated_delivery_from": "2025-12-24T06:00:00Z",
  "estimated_delivery_to": "2025-12-25T15:00:00Z",
  "original_estimated_delivery_from": "2025-12-24T06:00:00Z",
  "earliest_collection_capacity_date": null,
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
  "service_level_cut_off_time": "2025-12-20T13:00:00Z",
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
  "tracking_events": null,
  "collection_rescheduled": false,
  "delivery_rescheduled": false,
  "rating_reference": "f8c3c7aa-72d2-4cc7-bd38-650dba874e89",
  "has_rating": false,
  "payment_reference": "c008d00e-808e-4e74-a425-4511280c4717",
  "submitted_date": "2025-12-19T22:52:15.60285Z",
  "provider": {
    "name": null,
    "time_created": null,
    "invoice_counter": 0,
    "credit_note_counter": 0,
    "interhub_transfer_counter": 0,
    "hik_vision_last_tracking_event_id": 0
  },
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
    "balance": -785,
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
    "time_created": "2025-08-01T12:28:35.557146Z",
    "type": "business"
  },
  "delivery_address": {
    "id": 84087200,
    "gs_hash": null,
    "time_modified": "2025-12-19T22:52:15.235138Z",
    "hash": "3926075BCEF37DD2CBBE6CA939F1295C",
    "entered_address": "10 Midas Ave, Olympus AH, Pretoria, 0081, GP, South Africa",
    "company": "",
    "street_address": "10 Midas Ave",
    "local_area": "Olympus AH",
    "code": "0081",
    "city": "Pretoria",
    "zone": "GP",
    "country": "South Africa",
    "lat": -25.806656,
    "lng": 28.334732,
    "time_created": "2025-12-19T22:52:15.235138Z",
    "type": "residential"
  },
  "collection_contact": {
    "provider_id": 10,
    "shipment_id": 0,
    "name": "Cornel Rautenbach",
    "mobile_number": "",
    "email": "cornel+sandy@shiplogic.com"
  },
  "delivery_contact": {
    "provider_id": 10,
    "shipment_id": 0,
    "name": "",
    "mobile_number": "",
    "email": "james+sandyreceiver@shiplogic.com"
  },
  "parcels": [
    {
      "id": 110567809,
      "provider_id": 10,
      "status": "collection-assigned",
      "tracking_reference": "PZDRMT/1",
      "packaging": "Custom parcel",
      "shipment_id": 95464038,
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
      "time_created": "2025-12-19T22:52:15.235138Z",
      "time_modified": "2025-12-19T22:52:15.659152Z"
    }
  ],
  "original_shipment_information": {
    "original_service_level_code": "ECO",
    "original_service_level_name": "Economy"
  },
  "Rates": [
    {
      "id": 357455622,
      "provider_id": 10,
      "shipment_id": 95464038,
      "rate_revision_id": 22599,
      "name": "",
      "type": "base",
      "type_id": 148799,
      "value": 95,
      "vat": 12.3913,
      "vat_percentage": null,
      "vat_type": "standard",
      "valid_from": "2025-12-19T22:52:15.543928Z",
      "valid_until": null,
      "is_opt_in": false,
      "is_custom_charge": false,
      "is_quantity_based_charge": false,
      "quantity": 0,
      "billing_transaction_id": 100023340,
      "metadata": {
        "shipment_tracking_reference": "PZDRMT",
        "service_level_code": "ECO",
        "parcels": [
          {
            "submitted_Length_Cm": 20,
            "submitted_Width_Cm": 20,
            "submitted_Height_Cm": 10,
            "submitted_Weight_Kg": 2
          }
        ],
        "charged_weight": 2,
        "estimated_weight": 2,
        "shipment_id": 95464038
      }
    },
    {
      "id": 357455623,
      "provider_id": 10,
      "shipment_id": 95464038,
      "rate_revision_id": 22599,
      "name": "",
      "type": "rate_formula",
      "type_id": 5463716,
      "value": 95,
      "vat": 12.3913,
      "vat_percentage": 15,
      "vat_type": "standard",
      "valid_from": "2025-12-19T22:52:15.543928Z",
      "valid_until": null,
      "is_opt_in": false,
      "is_custom_charge": false,
      "is_quantity_based_charge": false,
      "quantity": 0,
      "billing_transaction_id": 100023340,
      "metadata": null
    },
    {
      "id": 357455624,
      "provider_id": 10,
      "shipment_id": 95464038,
      "rate_revision_id": 22599,
      "name": "",
      "type": "rate_group_extras",
      "type_id": 148342,
      "value": 25,
      "vat": 3.2609,
      "vat_percentage": null,
      "vat_type": "standard",
      "valid_from": "2025-12-19T22:52:15.543928Z",
      "valid_until": null,
      "is_opt_in": false,
      "is_custom_charge": false,
      "is_quantity_based_charge": false,
      "quantity": 0,
      "billing_transaction_id": 100023340,
      "metadata": null
    }
  ]
}

```

## Success Criteria
A request is considered successful when the API returns a success response and a shipment identifier is generated. Once successful, the shipment exists as a persistent record in the system.

## Portal Visibility
All successfully created shipments can be viewed and managed in the logistics portal.

Shipments created through this API will appear in the portal at:
https://sandbox.shiplogic.com/shipments

Access to the portal will be provided separately.

## Notes for Testers
Rates calculated via the rates endpoint are not visible in the portal. Only shipments created via this endpoint are persisted and displayed. If a shipment is not visible in the portal, it means the shipment was not successfully created.
