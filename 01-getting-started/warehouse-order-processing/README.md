# Warehouse Order Processing Automation

This workflow was completed during the **Getting Started** module of the official n8n Academy QS101 Quickstart course.

## Objective

Automate the retrieval, classification, aggregation, storage, and notification of warehouse order data.

## Workflow logic

1. Start manually or every Monday at 09:00.
2. Retrieve warehouse orders through an authenticated HTTP request.
3. Select orders where `orderStatus` is `processing` and `employeeName` is `Mario`.
4. Calculate order counts and monetary totals with JavaScript Code nodes.
5. Upsert selected order records into an n8n Data Table.
6. Send a summary notification through Discord.

## Import

1. Open the n8n workflow editor.
2. Select **Import from File**.
3. Import `workflow.json`.
4. Replace `YOUR_ASSESSMENT_ID` or adapt the HTTP request to your own API.
5. Configure your HTTP Header Auth and Discord Webhook credentials.
6. Create the required `orders` Data Table.
7. Review the `America/Sao_Paulo` timezone before activation.

The public export contains no credentials or private instance identifiers.
