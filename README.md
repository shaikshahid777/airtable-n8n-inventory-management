# ⚡ Airtable Inventory Management & Automation

<p align="center"><strong>No-Code Relational Inventory • Airtable REST API • n8n Automation</strong></p>

<p align="center">
<a href="https://airtable.com/appnfSULdENuSD8IG/tbloqBHmv8NNK7shp/viwyqYFr8QfnfVzmN?blocks=hide">🗃️ Open Airtable</a> ·
<a href="https://mohammad-shaheed.app.n8n.cloud/workflow/PLpnQooPznafZZxU">⚙️ Open n8n Workflow</a> ·
<a href="https://www.loom.com/share/13b4bb591c2349e3b48ef9aab666e7d4">🎥 Watch Demo</a> ·
<a href="./docs/PROJECT-DOCUMENTATION.md">📘 Documentation</a>
</p>

<p align="center">
<img src="https://img.shields.io/badge/Airtable-Database-18BFFF?style=for-the-badge" alt="Airtable">
<img src="https://img.shields.io/badge/n8n-Automation-EA4B71?style=for-the-badge" alt="n8n">
<img src="https://img.shields.io/badge/REST%20API-Integrated-111827?style=for-the-badge" alt="REST API">
<img src="https://img.shields.io/badge/Status-Tested-16A34A?style=for-the-badge" alt="Tested">
</p>

---

## 🎯 Project Snapshot

This project demonstrates a relational inventory system in Airtable connected to n8n through REST API calls.

### Core capabilities

- Relational Inventory and Suppliers tables
- Linked supplier records
- Inventory retrieval through Airtable REST API
- Supplier retrieval through Airtable REST API
- Programmatic inventory record creation
- Low-stock filtering with the formula {Qty}<10
- Inventory quantity update and validation
- Product image attachment evidence

The supplied technical assessment report documents the implementation and screenshots across five pages. fileciteturn4file0L2-L9

## 🧩 Architecture

<pre>
Manual Trigger
      │
      ├── GET Inventory Records ────────► Airtable Inventory
      │
      ├── GET Supplier Records ─────────► Airtable Suppliers
      │
      ├── POST Create Inventory Record ─► Airtable Inventory
      │
      ├── GET Low Stock Inventory ──────► Airtable Inventory
      │
      └── PATCH Update Quantity ────────► Airtable Inventory

Supplier Link: Inventory ──────────────► Suppliers
</pre>

## 🗃️ Airtable Data Model

### Inventory

| Field | Type | Purpose |
|---|---|---|
| Product Name | Single line text | Product identifier |
| Qty | Number | Current stock quantity |
| Price | Currency | Unit price |
| Product Image | Attachment | Product visual |
| Status | Single select | Stock condition |
| Supplier Link | Linked record | Related supplier |

### Suppliers

| Field | Type | Purpose |
|---|---|---|
| Supplier Name | Text | Supplier identifier |
| Contact Email | Email | Supplier contact |
| Inventory | Linked records | Related inventory |

The assessment documentation identifies Supplier Link as a linked-record field and documents the database schema. fileciteturn4file0L24-L34

## ⚙️ n8n Workflow

**Workflow:** Airtable - Get Inventory Records

| Node | Method | Function |
|---|---|---|
| Manual Trigger | — | Starts the workflow |
| Get Inventory Records | GET | Retrieves inventory |
| Get Supplier Records | GET | Retrieves suppliers |
| Create Inventory Record | POST | Creates a test inventory item |
| Get Low Stock Inventory | GET | Filters Qty below 10 |
| Update Test Inventory Quantity | PATCH | Updates the test record |

The exported workflow confirms these six nodes and their connections from the manual trigger. fileciteturn4file1L143-L171

## 🔍 Validation Scenario

### 01 — Create

**Test Wireless Keyboard**

- Qty: 5
- Price: 49.99
- Status: Low Stock
- Supplier: Acme Industrial Supplies

The workflow POST node creates this test record with the supplier relationship. fileciteturn4file1L60-L67

### 02 — Detect Low Stock

Filter formula:

    {Qty}<10

The low-stock node sends this formula to Airtable as a query parameter. fileciteturn4file1L86-L103

### 03 — Update

The test quantity is updated from 5 to 15 using PATCH. fileciteturn4file1L117-L129

### 04 — Validate

After the update, the low-stock query returns an empty records array.

This validates that the test record no longer satisfies the less-than-10 condition.

## 🖼️ Evidence

The project evidence sequence is:

1. Workflow overview
2. Inventory GET output
3. Supplier GET output
4. Create record output
5. Low-stock query
6. Quantity update
7. Final empty low-stock result

The submitted assessment PDF contains visual evidence for workflow architecture, supplier integration, inventory retrieval, record creation, filtering, and quantity validation. fileciteturn4file0L18-L22 fileciteturn4file0L38-L48

## 🔗 Quick Access

| Resource | Open |
|---|---|
| 🗃️ Airtable Base | [Open Airtable →](https://airtable.com/appnfSULdENuSD8IG/tbloqBHmv8NNK7shp/viwyqYFr8QfnfVzmN?blocks=hide) |
| ⚙️ n8n Workflow | [Open n8n →](https://mohammad-shaheed.app.n8n.cloud/workflow/PLpnQooPznafZZxU) |
| 🎥 Loom Demo | [Watch Demo →](https://www.loom.com/share/13b4bb591c2349e3b48ef9aab666e7d4) |
| 📘 Technical Documentation | [Open Documentation →](./docs/PROJECT-DOCUMENTATION.md) |
| 🧩 n8n JSON Export | [Open Workflow JSON →](./n8n/Airtable-Get-Inventory-Records.json) |

## 📁 Repository Structure

    airtable-n8n-inventory-management/
    ├── README.md
    ├── .gitignore
    ├── n8n/
    │   └── Airtable-Get-Inventory-Records.json
    ├── docs/
    │   └── PROJECT-DOCUMENTATION.md
    └── screenshots/
        └── README.md

## 🔐 Security

No Airtable Personal Access Token, API key, password, or secret value is intentionally documented here.

The n8n workflow references an Airtable credential by credential name; the actual token remains inside n8n. fileciteturn4file1L30-L33

---

<p align="center"><strong>Built as a technical assessment project using Airtable + n8n.</strong></p>
