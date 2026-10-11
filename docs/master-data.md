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



## Relationships Between Procurement Master Data

### 1. Material Master

The material master describes the material that a company purchases, stores, produces or sells.

Relevant information depends on the material and its intended use. Examples include the material description, unit of measure and logistics-related data.

In the classic SAP ERP university exercise, transaction `MM01` was used to create a material.

### 2. Supplier Master and Business Partner

Supplier data contains information required to work with a supplier. In the classic SAP ERP exercise, supplier information included general data, purchasing data and accounting data.

In SAP S/4HANA, the Business Partner approach is central to maintaining business partner data and assigning the relevant customer or supplier roles.

Classic transaction `XK01` is documented here as part of the university exercise, not as a recommendation for a modern S/4HANA workflow.

### 3. Purchasing Info Record

A purchasing info record maintains purchasing-related information for a material and a supplier.

It helps the purchasing process use relevant supplier-material information when creating purchasing documents.

The classic SAP ERP exercise used transaction `ME11` to create a purchasing info record.

### 4. Source List

A source list records relevant sources of supply for a material according to the applicable validity and purchasing settings.

It can support source determination, depending on the system configuration and procurement scenario.

The classic SAP ERP exercise used transaction `ME01` to maintain a source list.

### 5. How the Objects Work Together

The following questions help explain the relationships:

- **Material master:** What material is required?
- **Supplier master / Business Partner:** Which supplier is involved?
- **Purchasing info record:** What purchasing information is maintained for this supplier-material combination?
- **Source list:** Which sources of supply are relevant or permitted for the material?
- **Purchase order:** What has actually been ordered in this specific business transaction?

Master data supports business transactions, but it does not replace them. A purchase order documents a specific procurement event, whereas the master data provides reusable information for the process.

### 6. Business Impact of Master Data Quality

Incorrect or incomplete master data can lead to purchasing errors, delays and additional manual work.

Examples include:

- Incorrect material information
- Missing supplier data
- Inaccurate purchasing conditions
- Incomplete or outdated source-of-supply information

As a junior SAP consultant, it is important to understand how master data affects process execution and how to investigate potential data-related issues.

### 7. Scope of This Documentation

This section combines concepts covered in the classic SAP ERP university exercise with a conceptual description of SAP S/4HANA.

The described transactions and process relationships have not been validated through execution in a live SAP S/4HANA system.



## Master Data Quality: Procurement Validation Scenarios

### Business Context

In the PC production case, 30 additional hard drives must be procured to fulfill a customer order for 50 PCs.

Successful procurement depends not only on the purchasing documents but also on consistent and complete master data.

### Proposed Test Scenarios

| Test ID | Scenario | Expected Result |
|---|---|---|
| MD-001 | Material master contains an incorrect base unit of measure | Inconsistent quantity handling is identified and investigated |
| MD-002 | Required purchasing data for the supplier is missing | The missing data is identified before successful purchasing document processing |
| MD-003 | Purchasing info record contains an incorrect planned delivery time | The planning impact is identified and the relevant master data is reviewed |
| MD-004 | Source list contains an unsuitable or blocked source | Source determination follows the applicable source list settings |
| MD-005 | Correct material, supplier and purchasing master data are available | The procurement process can proceed without master-data-related issues |

### Consultant's Troubleshooting Approach

1. Record the user's description of the issue and the exact system message.
2. Identify the affected process step and organizational units.
3. Check the relevant material and supplier/Business Partner master data.
4. Review the purchasing info record and source list where applicable.
5. Consider other potential causes, including authorization or configuration issues.
6. Document the findings and coordinate the required correction.
7. Repeat the relevant process test and record the result.

### SAP ERP and SAP S/4HANA Context

The original university exercise used classic SAP ERP transactions such as MM01, XK01, ME11 and ME01. In SAP S/4HANA, the Business Partner concept is relevant for supplier master data management. The specific application and maintenance steps depend on the S/4HANA deployment and system configuration.

**Execution status:** All scenarios are conceptual. No live SAP S/4HANA execution or validation is claimed.