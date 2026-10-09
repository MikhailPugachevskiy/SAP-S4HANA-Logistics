# SAP Master Data: Logistics and Production

## 1. Purpose

This document describes the key master data objects used in the university SAP ERP case study for hardware production and sales.

Master data provides reusable information required to execute business processes. In the case study, customer, supplier, and material data support activities across sales, procurement, inventory management, and production.

## 2. Customer Master Data

Customer master data contains information needed to process customer-related business activities.

In the case study, a customer is required to create an inquiry, quotation, and sales order.

**Classic SAP ERP transaction in the university materials:** `XD01` – Create customer.

Typical business relevance:
- Sales documents reference the customer.
- Customer information supports order processing and delivery.
- Customer-related financial processes use relevant customer account data.

## 3. Supplier Master Data

Supplier master data contains information required for procurement and supplier-related accounting.

The university materials distinguish between:
- General data
- Purchasing data
- Accounting data

**Classic SAP ERP transaction in the university materials:** `XK01` – Create supplier.

Supplier data is relevant when components must be procured to support production.

## 4. Material Master Data

The material master describes products, components, and other materials used by business processes.

In the hardware case study, the finished PC and its components are represented as materials.

**Classic SAP ERP transaction in the university materials:** `MM01` – Create material.

Business relevance:
- Procurement uses material information to order components.
- Inventory management tracks material stock and movements.
- Material requirements planning evaluates demand and supply.
- Production uses material information to plan and execute manufacturing.

## 5. Bill of Materials (BOM)

A bill of materials describes the components required to manufacture a product.

**Classic SAP ERP transaction in the university materials:** `CS01` – Create bill of materials.

Simplified example:

| Finished product | Component | Quantity |
|---|---|---:|
| PC | Housing | 1 |
| PC | Hard drive | 1 |

The quantities are illustrative of the simplified university scenario and are not a specification for a real computer.

The bill of materials answers the question:

**Which components are required to make the product?**

## 6. Routing

A routing describes the manufacturing operations required to produce a material.

**Classic SAP ERP transaction in the university materials:** `CA01` – Create routing.

The routing answers the question:

**Which manufacturing steps are required, and in what sequence?**

The bill of materials and routing serve different purposes but are both relevant to production planning and execution.

## 7. Purchasing Information Record

The purchasing information record links a material with supplier-related purchasing information.

**Classic SAP ERP transaction in the university materials:** `ME11` – Create purchasing information record.

It supports the procurement process by maintaining information relevant to purchasing a particular material from a supplier.

## 8. Source List

The source list records permitted or relevant sources of supply for a material over a defined period, depending on the system configuration.

**Classic SAP ERP transaction in the university materials:** `ME01` – Maintain source list.

It supports source determination during procurement.

## 9. Pricing Conditions

Pricing conditions define pricing information used by relevant business processes.

**Classic SAP ERP transaction in the university materials:** `VK31` – Maintain conditions.

In the university case study, pricing conditions are part of the preparation for the sales process.

## 10. Master Data and Transaction Data

Master data provides reusable information, while transaction data and business documents record specific business activities.

Examples:

| Master data | Business transaction or document |
|---|---|
| Customer | Sales order |
| Supplier | Purchase order |
| Material | Goods receipt |
| Bill of materials | Production planning |
| Routing | Production execution |

These relationships are simplified examples. The exact dependencies vary by process and SAP configuration.

## 11. SAP S/4HANA Learning Note

The university case study uses classic SAP ERP transactions, including `XD01` and `XK01` for customer and supplier creation.

In SAP S/4HANA, the Business Partner concept plays a central role in maintaining customer and supplier master data. The classic transactions listed above should therefore not be assumed to represent the preferred workflow in every S/4HANA system.

This distinction is important when transferring knowledge from a classic SAP ERP learning environment to modern SAP projects.

## 12. Key Takeaways

- Customer and supplier master data support sales and procurement.
- Material master data is central to logistics and production.
- The bill of materials describes required components.
- The routing describes manufacturing operations.
- Purchasing information records and source lists support procurement.
- Master data must be maintained correctly for business processes to work reliably.