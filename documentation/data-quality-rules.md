# Data Quality Rules

## Properties

- property_id must be unique
- property_id must not be null
- property_name must not be null
- property_type must use approved values:
  - Office
  - Retail
  - Mixed Use
- lettable_area_sqft must be greater than 0
- property_value must be greater than 0

## Tenants

- tenant_id must be unique
- tenant_id must not be null
- tenant_name must not be null
- industry must not be null
- industry must use approved categories

## Leases

- lease_id must be unique
- tenant_id must exist in tenants
- property_id must exist in properties
- start_date must be before end_date
- annual_rent must be greater than 0

## Maintenance

- maintenance_id must be unique
- property_id must exist in properties
- date must be valid
- category must not be null
- cost must be greater than or equal to 0

## Finance

- transaction_id must be unique
- property_id must exist in properties
- date must be valid
- transaction_type must not be null
- amount must be greater than or equal to 0

## Cross-Dataset Rules

- Every lease must reference an existing tenant
- Every lease must reference an existing property
- Every maintenance record must reference an existing property
- Every finance transaction must reference an existing property
- Financial transactions should be investigated when amounts are unusually large
- Duplicate transaction IDs must be rejected or quarantined
