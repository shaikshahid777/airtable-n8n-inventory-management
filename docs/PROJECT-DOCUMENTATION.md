# Technical Documentation

## Airtable Inventory Management & Automation

### Objective

Demonstrate a relational Airtable inventory database integrated with n8n through REST API operations.

### Airtable Schema

**Inventory**
- Product Name
- Qty
- Price
- Product Image
- Status
- Supplier Link

**Suppliers**
- Supplier Name
- Contact Email
- Linked Inventory records

### n8n Workflow

1. Manual Trigger
2. Get Inventory Records
3. Get Supplier Records
4. Create Inventory Record
5. Get Low Stock Inventory
6. Update Test Inventory Quantity

### API Operations

- GET Inventory records
- GET Supplier records
- POST test inventory record
- GET low-stock records using `{Qty}<10`
- PATCH test quantity from 5 to 15

### Validation

The test item **Test Wireless Keyboard** was created with Qty 5 and Low Stock status. It appeared in the low-stock query. After the quantity was updated to 15, the low-stock query returned an empty records array.

The final test item includes the **600x400.png** product image attachment.

### Evidence

The supplied assessment PDF contains the project screenshots and validation evidence. The repository also provides the n8n workflow export and direct links to the live project resources.

### Live Resources

- [Airtable Base](https://airtable.com/appnfSULdENuSD8IG/tbloqBHmv8NNK7shp/viwyqYfr8QfnfVzmN?blocks=hide)
- [n8n Workflow](https://mohammad-shaheed.app.n8n.cloud/workflow/PLpnQooPznafZZxU)
- [Loom Demo](https://www.loom.com/share/13b4bb591c2349e3b48ef9aab666e7d4)
- [GitHub Repository](https://github.com/shaikshahid777/airtable-n8n-inventory-management)
