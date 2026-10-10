# SAP S/4HANA – Procurement Process Case Study

## 1. Business Scenario

A company manufactures and sells hardware products. During production planning, the system identifies that additional components are required to fulfil a customer order.

The purchasing department must procure the missing components so that production can continue without unnecessary delays.

This case study documents the procurement process from the identification of a material requirement through purchasing, goods receipt and invoice verification.

**Scope:** This is a process design and learning exercise. The process has not been executed in a live SAP S/4HANA system.

## 2. Business Objective

The objective is to ensure that:

- Required components are available in the correct quantity.
- Purchasing documents contain the relevant material, supplier, quantity and delivery information.
- Goods receipts are recorded correctly.
- Supplier invoices can be checked against the relevant purchasing and goods receipt documents.
- Procurement activities are integrated with inventory management, production planning and accounting.

## 3. End-to-End Procurement Process

### Step 1: Identify the Material Requirement

Material requirements planning identifies a shortage based on existing stock, requirements and planning parameters.

In the university SAP ERP exercise, transaction MD04 was used to review the stock/requirements situation, while MD02 was used to execute MRP.

**Expected outcome:** The material shortage is identified and a suitable procurement proposal is available where required.

### Step 2: Create or Review the Purchase Requisition

A purchase requisition communicates an internal requirement to the purchasing department.

The requester or planning process specifies the required material, quantity and delivery date.

**Expected outcome:** The purchasing department can review the requirement and initiate procurement.

### Step 3: Determine the Source of Supply

Purchasing reviews the available suppliers and relevant purchasing information.

Relevant master data may include:

- Supplier or Business Partner data
- Material master data
- Purchasing info records
- Source lists, where applicable
- Purchasing conditions and delivery information

**Expected outcome:** An appropriate source of supply is selected according to the company's purchasing rules.

### Step 4: Create the Purchase Order

The purchasing department creates a purchase order based on the requirement and selected source of supply.

The purchase order specifies the supplier, material, quantity, delivery date, price and other relevant terms.

**Expected outcome:** The supplier receives an order containing the agreed purchasing requirements.

### Step 5: Post the Goods Receipt

When the supplier delivers the material, the receiving department checks the delivery and records the goods receipt.

In the classic SAP ERP university exercise, transaction MIGO was used for goods receipt.

The goods movement updates the relevant inventory information according to the configured process.

**Expected outcome:** The received quantity is recorded and the material is available for subsequent business activities, subject to any applicable stock or inspection restrictions.

### Step 6: Verify the Supplier Invoice

Accounts payable or the responsible finance team checks the supplier invoice against the purchasing documents and relevant goods receipt information.

The check helps identify discrepancies such as quantity differences, price differences or missing documentation.

**Expected outcome:** The invoice is accepted for further processing or a discrepancy is investigated.

### Step 7: Complete the Procurement Cycle

After the relevant checks and approvals, the supplier invoice proceeds through the company's payment process.

The procurement process is connected to inventory management and financial accounting.

**Expected outcome:** The procurement transaction is documented and the resulting inventory and financial information are consistent with the recorded business activities.

## 4. Process Integration

Procurement is not an isolated activity.

| Integrated area | Relationship |
|---|---|
| Production planning | Identifies component requirements |
| Purchasing | Selects suppliers and creates purchase orders |
| Inventory management | Records goods receipts and stock changes |
| Accounts payable | Verifies supplier invoices |
| Financial accounting | Records the relevant financial impact |

## 5. Classic SAP ERP and SAP S/4HANA

The university exercise used a classic SAP ERP training environment and transaction codes such as MD04, MD02 and MIGO.

SAP S/4HANA provides modern applications and process capabilities for sourcing and procurement. The precise applications and steps depend on the system edition, configuration and business scenario.

This case study therefore distinguishes the documented classic ERP exercise from the S/4HANA concepts being studied.

## 6. Initial Test Scenarios

| Test ID | Scenario | Expected result |
|---|---|---|
| PROC-001 | A material shortage is identified | The requirement is visible for planning or purchasing |
| PROC-002 | A purchase requisition is reviewed | Material, quantity and required date are checked |
| PROC-003 | A suitable supplier is selected | The selected source meets the purchasing requirements |
| PROC-004 | A purchase order is created | The order contains the required purchasing information |
| PROC-005 | Goods are received | The receipt is recorded against the relevant purchasing document |
| PROC-006 | A supplier invoice is checked | Differences are identified and handled according to the process |

**Test status:** Designed – execution not performed.

## 7. Open Questions for Further Learning

- Which organizational units are required for purchasing in the target SAP S/4HANA system?
- Which master data and configuration determine the source of supply?
- How are approval workflows handled?
- How are quantity and price differences handled during invoice verification?
- Which SAP Fiori applications support each process step in the target system?

These questions will be investigated during further SAP Learning activities.