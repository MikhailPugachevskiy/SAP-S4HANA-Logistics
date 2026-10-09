# Test Case: End-to-End Hardware Sales and Production Process

## 1. Test Case Overview

| Attribute | Description |
|---|---|
| Test Case ID | TC-001 |
| Process | Sales, procurement, production, and delivery |
| SAP areas | SD, MM, PP, FI |
| Test type | End-to-end business process test |
| Status | Designed – execution not performed |
| Reference | University SAP ERP hardware case study |

## 2. Business Objective

Verify that a customer order can be processed through the relevant business activities, from sales order creation to delivery, billing, and incoming payment.

If finished products or required components are unavailable, the process must account for the relevant inventory, procurement, and production requirements.

**Important:** This test case is documented for learning purposes. It has not been executed in a live SAP system.

## 3. Preconditions

Before executing the test, the following conditions should be checked:

- A valid customer master record exists.
- The finished product and required component materials exist.
- The bill of materials and routing are maintained where required.
- The relevant plant and storage locations are configured.
- Purchasing and supplier data are available if procurement is required.
- Pricing conditions are maintained.
- The user has the necessary authorizations.
- The relevant stock and requirements situation can be reviewed.

## 4. Test Data

| Attribute | Value |
|---|---|
| Product | PC |
| Initial customer inquiry | 200 PCs |
| Quotation quantity | 200 PCs |
| Quotation price | €1,000 per PC |
| Confirmed order quantity | 50 PCs |
| Total order value at quotation price | €50,000 before any applicable adjustments |

The value calculation assumes that the quotation price is applied unchanged to all 50 ordered PCs. Taxes, discounts, freight, and other pricing conditions are not included.

## 5. Test Steps and Expected Results

| Step | Action | Expected result |
|---|---|---|
| 1 | Create a customer inquiry | Inquiry is saved and can be displayed |
| 2 | Create a quotation referencing the inquiry | Quotation contains the relevant customer and product data |
| 3 | Create a sales order for 50 PCs | Sales order is saved with the correct quantity |
| 4 | Review stock and requirements | The current supply situation is visible |
| 5 | Run material requirements planning if needed | Planning results reflect the relevant requirements and supply situation |
| 6 | Procure missing components if required | Purchase order and subsequent goods receipt are recorded |
| 7 | Execute production if required | Production is recorded and the finished product becomes available according to the configured process |
| 8 | Create the delivery | Delivery document is created for the relevant order quantity |
| 9 | Post goods issue | Goods issue is recorded and inventory is updated accordingly |
| 10 | Create the billing document | Billing document is created with the expected quantities and pricing |
| 11 | Record incoming payment | Payment is posted and the relevant customer open item is cleared or updated according to the payment and accounting configuration |

## 6. Validation Points

During execution, the tester should verify:

- The sales order references the correct customer and product.
- The order quantity is 50 PCs.
- Stock and requirements are consistent with the planning results.
- Missing components are procured where necessary.
- Production quantities and component consumption are consistent with the order.
- The delivery quantity matches the intended fulfilment quantity.
- Goods issue is recorded correctly.
- Billing reflects the delivered quantity and applicable pricing conditions.
- The incoming payment is recorded correctly in accounting.

## 7. Defect Examples

Potential issues that could be identified during testing include:

- Missing or incorrect master data.
- Insufficient stock not reflected as expected in planning.
- Missing purchasing data or supplier information.
- Incorrect production quantities.
- Delivery quantity inconsistent with the sales order.
- Incorrect billing amount.
- Incoming payment not correctly assigned to the customer invoice.

These are hypothetical test examples, not defects observed in an actual SAP system.

## 8. Test Result

**Execution status:** Not executed.

The test can be marked as passed only after all applicable steps have been executed and the expected results have been verified in the target SAP system.

## 9. Learning Outcome

This test case demonstrates how an integrated business process can be translated into documented test steps, expected results, and validation points.

It also illustrates the connection between sales, material requirements planning, procurement, production, shipping, and financial accounting.