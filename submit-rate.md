# Shipping Rates API – Create Rate Request

## Endpoint
POST /rates

## Purpose
This endpoint is used to retrieve shipping rate quotations based on pickup and delivery locations, parcel dimensions, weight, and the selected logistics provider. After submitting the request, the system validates the shipment data, calculates chargeable weight, applies provider pricing rules, and returns one or more calculated rate options. This endpoint does not create shipments and does not schedule collections. It only returns rate quotations.

## Typical Use Cases
This endpoint is typically used to display available shipping options to end users, compare delivery times and prices, validate shipping costs before shipment creation, and perform integration or automated testing scenarios.

## Request Overview
The request represents a shipping scenario including the logistics provider, collection address, delivery address, and one or more parcels with submitted dimensions and weight. The pricing calculation considers both actual and volumetric weight and applies provider-specific rules to determine the final charged weight.

## Request Example

```json
{
    "provider_id": 1,
    "collection_address": {
      "type": "business",
      "street_address": "116 Lois Avenue",
      "local_area": "Menlyn",
      "city": "Pretoria",
      "zone": "Gauteng",
      "country": "ZA",
      "code": "0181"
    },
    "delivery_address": {
      "type": "residential",
      "street_address": "10 Midas Avenue",
      "local_area": "Olympus AH",
      "city": "Pretoria",
      "zone": "Gauteng",
      "country": "ZA",
      "code": "0081"
    },
    "parcels": [
      {
        "packaging": "Box 1",
        "parcel_description": "Box 1",
        "submitted_length_cm": 20,
        "submitted_width_cm": 20,
        "submitted_height_cm": 10,
        "submitted_weight_kg": 2
      }
    ]
  }

```

## Response Overview
A successful response returns an operation status, optional service day information, and a list of calculated rates, each representing a possible shipping service. Each rate includes pricing information, service level details, delivery and collection estimates, and the weight calculation used for charging.

## Response Example
```json
{
  "message": "Success",
  "service_Days": {
    "collection_Service_Days": null,
    "delivery_Service_Days": null
  },
  "rates": [
    {
      "rate": 86.25,
      "rate_Excluding_Vat": 75,
      "base_Rate": {
        "charge_Per_Parcel": [
          86.25
        ],
        "charge": 86.25,
        "group_Name": "Default group",
        "vat": 11.25,
        "vat_Type": "standard",
        "vat_Percentage": 15,
        "rate_Formula_Type": "formula",
        "total_Calculated_Weight": 2
      },
      "service_Level": {
        "id": 139843,
        "code": "LSF",
        "name": "Local Sameday Flyer",
        "description": "",
        "delivery_Date_From": "2025-12-19T07:00:00+00:00",
        "delivery_Date_To": "2025-12-19T13:00:00+00:00",
        "collection_Date": "2025-12-19T06:00:00+00:00",
        "collection_Cut_Off_Time": "2025-12-19T08:30:00+00:00",
        "vat_Type": "standard",
        "insurance_Disabled": false
      },
      "surcharges": [],
      "rate_Adjustments": [],
      "time_Based_Rate_Adjustments": [],
      "extras": [],
      "charged_Weight": 2,
      "actual_Weight": 2,
      "volumetric_Weight": 1
    },
    {
      "rate": 86.25,
      "rate_Excluding_Vat": 75,
      "base_Rate": {
        "charge_Per_Parcel": [
          86.25
        ],
        "charge": 86.25,
        "group_Name": "Default group",
        "vat": 11.25,
        "vat_Type": "standard",
        "vat_Percentage": 15,
        "rate_Formula_Type": "formula",
        "total_Calculated_Weight": 2
      },
      "service_Level": {
        "id": 139844,
        "code": "LOF",
        "name": "Local Overnight Flyer",
        "description": "",
        "delivery_Date_From": "2025-12-19T14:00:00+00:00",
        "delivery_Date_To": "2025-12-22T13:00:00+00:00",
        "collection_Date": "2025-12-19T06:00:00+00:00",
        "collection_Cut_Off_Time": "2025-12-19T12:00:00+00:00",
        "vat_Type": "standard",
        "insurance_Disabled": false
      },
      "surcharges": [],
      "rate_Adjustments": [],
      "time_Based_Rate_Adjustments": [],
      "extras": [],
      "charged_Weight": 2,
      "actual_Weight": 2,
      "volumetric_Weight": 1
    },
    {
      "rate": 95,
      "rate_Excluding_Vat": 82.60869565217392,
      "base_Rate": {
        "charge_Per_Parcel": [
          95
        ],
        "charge": 95,
        "group_Name": "Default group",
        "vat": 12.391304347826079,
        "vat_Type": "standard",
        "vat_Percentage": 15,
        "rate_Formula_Type": "flat",
        "total_Calculated_Weight": 2
      },
      "service_Level": {
        "id": 139841,
        "code": "ECO",
        "name": "Economy",
        "description": "Delivered within 2-3 days",
        "delivery_Date_From": "2025-12-23T06:00:00+00:00",
        "delivery_Date_To": "2025-12-24T15:00:00+00:00",
        "collection_Date": "2025-12-19T06:00:00+00:00",
        "collection_Cut_Off_Time": "2025-12-19T13:00:00+00:00",
        "vat_Type": "standard",
        "insurance_Disabled": false
      },
      "surcharges": [],
      "rate_Adjustments": [],
      "time_Based_Rate_Adjustments": [],
      "extras": [],
      "charged_Weight": 2,
      "actual_Weight": 2,
      "volumetric_Weight": 1
    },
    {
      "rate": 103.5,
      "rate_Excluding_Vat": 90,
      "base_Rate": {
        "charge_Per_Parcel": [
          103.5
        ],
        "charge": 103.5,
        "group_Name": "Default group",
        "vat": 13.5,
        "vat_Type": "standard",
        "vat_Percentage": 15,
        "rate_Formula_Type": "formula",
        "total_Calculated_Weight": 2
      },
      "service_Level": {
        "id": 139845,
        "code": "LSE",
        "name": "Local Same Day Economy",
        "description": "",
        "delivery_Date_From": "2025-12-19T07:00:00+00:00",
        "delivery_Date_To": "2025-12-19T13:00:00+00:00",
        "collection_Date": "2025-12-19T06:00:00+00:00",
        "collection_Cut_Off_Time": "2025-12-19T08:30:00+00:00",
        "vat_Type": "standard",
        "insurance_Disabled": false
      },
      "surcharges": [],
      "rate_Adjustments": [],
      "time_Based_Rate_Adjustments": [],
      "extras": [],
      "charged_Weight": 2,
      "actual_Weight": 2,
      "volumetric_Weight": 1
    },
    {
      "rate": 560,
      "rate_Excluding_Vat": 486.9565217391305,
      "base_Rate": {
        "charge_Per_Parcel": [
          560
        ],
        "charge": 560,
        "group_Name": "Default group",
        "vat": 73.0434782608695,
        "vat_Type": "standard",
        "vat_Percentage": 15,
        "rate_Formula_Type": "flat",
        "total_Calculated_Weight": 2
      },
      "service_Level": {
        "id": 139846,
        "code": "LSX",
        "name": "Local Sameday Express",
        "description": "Collection sameday after 8:00 but before 15:00, delivery within 90 minutes.  ",
        "delivery_Date_From": "2025-12-19T07:00:00+00:00",
        "delivery_Date_To": "2025-12-19T13:00:00+00:00",
        "collection_Date": "2025-12-19T06:00:00+00:00",
        "collection_Cut_Off_Time": "2025-12-19T12:00:00+00:00",
        "vat_Type": "standard",
        "insurance_Disabled": false
      },
      "surcharges": [],
      "rate_Adjustments": [],
      "time_Based_Rate_Adjustments": [],
      "extras": [],
      "charged_Weight": 2,
      "actual_Weight": 2,
      "volumetric_Weight": 1
    }
  ]
}

```

## Rates
Each item in the rates array represents a shipping option. Rates may vary by service speed such as Same Day, Overnight, Economy, or Express, by cut-off times, by delivery windows, and by pricing model such as flat or formula-based. Multiple rates can be returned for the same request.

## Pricing and Weight Calculation
The final rate is calculated based on the actual weight, volumetric weight, and charged weight, which is the highest value between actual and volumetric weight, combined with the base rate and applicable VAT and tax rules. Returned values may include the total rate including VAT, the rate excluding VAT, and the VAT amount and percentage.

## Service Levels
Each rate contains a service level defining the delivery type, estimated collection and delivery dates, cut-off times, and insurance availability. Service availability depends on address data, parcel details, and provider configuration.

## Success Criteria
A request is considered successful when the message equals "Success", the rates array contains at least one item, and each rate includes a valid service level and calculated price.

## Notes for Testers
Missing service day values do not indicate an error. Prices may vary depending on request time and service cut-off rules. VAT rules depend on provider configuration. This endpoint returns quotations only and does not confirm or create deliveries.
