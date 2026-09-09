# Generating Reports

Combines order and customer data, generates a European sales report, and sends a regional summary to Discord.

![Generating Reports workflow](../assets/generating-reports.svg)

## Flow

1. Retrieve 30 authenticated order records.
2. Read 10 enriched customer records from the `customers` Data Table.
3. Merge both datasets on `customerID`.
4. Calculate `orderTotal` as `orderPrice * quantity`.
5. Sort orders by total value.
6. Filter European orders and convert them to CSV.
7. Upload the European report to the course reporting endpoint.
8. Aggregate totals and order counts by region.
9. Send four formatted regional summaries to Discord.

## Expected result

- 30 merged order records
- 12 European orders
- European total: `$3,590.54`
- 4 regional summary items
- Grand total: `$7,586.52`

## Setup

Import `workflow.json`, select your `customers` Data Table, replace `YOUR_ASSESSMENT_ID`, and configure authorized Header Auth and Discord Webhook credentials. Never commit real credentials or assessment identifiers.
