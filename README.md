# Airtable Inventory Management & Automation

A technical assessment project demonstrating a no-code relational inventory database in Airtable integrated with n8n through the Airtable REST API.

## Airtable Database

### Inventory
- Product Name — Single Line Text
- Qty — Number
- Price — Currency
- Product Image — Attachment
- Status — Single Select
- Supplier Link — Linked Record

### Suppliers
- Supplier Name
- Contact Email
- Linked Inventory records

The Supplier Link field connects inventory products to their associated supplier records.

## n8n Workflow

Workflow: **Airtable - Get Inventory Records**

Nodes:
1. Manual Trigger
2. Get Inventory Records
3. Get Supplier Records
4. Create Inventory Record
5. Get Low Stock Inventory
6. Update Test Inventory Quantity

### Validation

The test product **Test Wireless Keyboard** was created with Qty 5, Price 49.99, Status Low Stock, and linked to Acme Industrial Supplies.

The low-stock query uses:
`{Qty}<10`

After updating the quantity from 5 to 15, the low-stock query returned an empty records array.

The final test record also contains the image attachment **600x400.png**.

## Links

- [Airtable Base](https://airtable.com/appnfSULdENuSD8IG/tbloqBHmv8NNK7shp/viwyqYfr8QfnfVzmN?blocks=hide)
- [n8n Workflow](https://mohammad-shaheed.app.n8n.cloud/workflow/PLpnQooPznafZZxU)
- [Loom Demo](https://www.loom.com/share/13b4bb591c2349e3b48ef9aab666e7d4)
- [Technical Documentation PDF](./docs/Airtable-Inventory-Management-Automation-Technical-Documentation.pdf)

## Repository Structure

```
airtable-n8n-inventory-management/
├── README.md
├── n8n/
│   └── Airtable-Get-Inventory-Records.json
├── docs/
│   └── Airtable-Inventory-Management-Automation-Technical-Documentation.pdf
├── screenshots/
│   ├── 01-workflow-overview.png
│   ├── 02-get-inventory-records.png
│   ├── 03-get-supplier-records.png
│   ├── 04-create-inventory-record.png
│   ├── 05-low-stock-result.png
│   ├── 06-update-quantity-result.png
│   └── 07-final-low-stock-empty.png
└── .gitignore
```

## Security

Never commit Airtable Personal Access Tokens, API keys, passwords, or other secrets.
