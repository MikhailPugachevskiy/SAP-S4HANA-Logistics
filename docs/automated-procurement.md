# Automated Procurement – Conceptual Case Study

## 1. Business Scenario

The fictional PC manufacturing company requires 30 additional hard drives to fulfill a customer order for 50 PCs.

The company wants to evaluate whether recurring and standardized procurement requirements can be processed with less manual purchasing effort.

The proposed scenario assumes that suitable master data, source determination and relevant system settings are available.

## 2. Proposed Process

1. A material shortage is identified through requirements planning.
2. A purchase requisition is created for the missing quantity.
3. A suitable source of supply is determined.
4. If the applicable prerequisites are fulfilled, the purchase requisition is converted into a purchase order through an automated process.
5. The goods receipt is recorded when the ordered materials arrive.
6. Supplier invoice processing follows the applicable verification procedure.

## 3. Prerequisites to Evaluate

- Complete and consistent material master data.
- Suitable supplier/Business Partner purchasing data.
- Valid source-of-supply information.
- Required settings for automated purchasing document processing.
- Defined responsibilities, controls and exception-handling procedures.

## 4. Proposed Validation Scenarios

| Test ID | Scenario | Expected Result |
|---|---|---|
| AUTO-001 | Valid purchase requisition with all required prerequisites | Automatic processing can proceed according to the configured rules |
| AUTO-002 | No suitable source of supply is available | The issue is identified and the requirement is handled as an exception |
| AUTO-003 | Required purchasing master data is incomplete | Incorrect automatic processing is prevented or flagged according to system behavior |
| AUTO-004 | Purchase requisition is successfully converted | The resulting purchase order contains the expected purchasing data |
| AUTO-005 | A procurement requirement does not meet automation conditions | The requirement follows the defined exception or manual processing procedure |

## 5. Consultant's Perspective

Automation should be evaluated based on the business process, data quality and operational requirements. The consultant should identify suitable standard scenarios, document prerequisites, define exception handling and prepare test cases before productive implementation.

**Execution status:** Conceptual case study only. No automatic purchase order creation has been configured or executed in a live SAP S/4HANA environment.