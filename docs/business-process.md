# End-to-End Business Process: Hardware Production and Sales

## 1. Business Scenario

The case study describes an integrated business process for the production and sale of hardware products.

A customer initially requests 200 PCs. The company prepares a quotation for 200 PCs at €1,000 per unit. The customer subsequently places an order for 50 PCs.

If the available finished-goods inventory is insufficient, production must be planned. Missing components are procured before production can be completed.

The process ends with delivery, billing, and incoming payment.

## 2. Process Overview

| Step | Business activity | SAP area | Classic SAP ERP transaction |
|---|---|---|---|
| 1 | Create customer inquiry | SD | VA11 |
| 2 | Create quotation | SD | VA21 |
| 3 | Create sales order | SD | VA01 |
| 4 | Review stock and requirements | Materials planning | MD04 |
| 5 | Run material requirements planning | Materials planning | MD02 |
| 6 | Create or convert production order | PP | Follow the process in MD04 |
| 7 | Create purchase order for missing components | MM | Follow the process in MD04 |
| 8 | Post goods receipt | MM | MIGO |
| 9 | Withdraw components for production | Production / inventory | MB1A |
| 10 | Confirm production completion | PP | CO15 |
| 11 | Create delivery | SD | VL01N |
| 12 | Create transport order | Warehouse / shipping process in the lab | LT03 |
| 13 | Post goods issue | Shipping / inventory | VL02N |
| 14 | Create billing document | SD / billing | VF01 |
| 15 | Post incoming customer payment | FI | F-28 |

**Note:** This table reflects the classic SAP ERP learning environment described in the university materials. The exact implementation and available transactions depend on the SAP system and its configuration.

## 3. Process Details

### 3.1 Sales Inquiry, Quotation, and Sales Order

The sales process begins with a customer inquiry.

- `VA11` – Create inquiry.
- `VA21` – Create quotation.
- `VA01` – Create sales order.

The quotation references the inquiry. The customer subsequently confirms an order for 50 PCs.

### 3.2 Material Requirements Planning

The company checks whether enough finished products are available to fulfil the order.

- `MD04` – Review the current stock and requirements situation.
- `MD02` – Execute the MRP run.

If additional production is required, a planned order can be converted into a production order. If components are missing, procurement may be necessary.

### 3.3 Procurement

Missing components are procured to support production.

The case study includes creating purchase orders from purchase requisitions and recording goods receipt.

- `MIGO` – Post goods receipt for the purchase order.

After the goods receipt, the received components become available for subsequent process steps, subject to the relevant stock and posting conditions.

### 3.4 Production

The production process uses the product's bill of materials and routing.

- `MB1A` – Withdraw components from inventory in the classic lab.
- `CO15` – Confirm production completion.

The completed product can then become available for fulfilment of the customer order.

### 3.5 Delivery and Goods Issue

The delivery process prepares the products for shipment.

- `VL01N` – Create delivery.
- `LT03` – Create transport order in the lab scenario.
- `VL02N` – Process delivery and post goods issue.

The goods issue records the goods leaving inventory.

### 3.6 Billing and Incoming Payment

After goods issue, the company creates the customer billing document and records the incoming payment.

- `VF01` – Create billing document.
- `F-28` – Post incoming payment.

The case study therefore demonstrates how logistics activities connect with financial processes.

## 4. Key Master Data

The case study uses several types of master data:

- Customer
- Supplier
- Material
- Bill of materials
- Routing
- Purchasing information record
- Source list
- Pricing conditions

These objects support the execution of the business process.

## 5. Key Learning Points

1. A customer order can influence production and procurement requirements.
2. Material requirements planning connects demand with supply.
3. The bill of materials describes which components are needed for a product.
4. The routing describes the manufacturing sequence.
5. Goods receipt and goods issue record inventory movements.
6. Delivery, billing, and incoming payment represent connected but distinct process steps.
7. SAP integrates business activities across sales, materials management, production, and finance.

## 6. Scope

This document describes the classic SAP ERP university case study. It is a learning document, not a record of a live S/4HANA implementation.

The differences between the classic learning environment and SAP S/4HANA will be documented separately.