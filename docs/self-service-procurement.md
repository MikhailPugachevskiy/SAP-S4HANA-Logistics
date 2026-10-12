# Self-Service Procurement – Monitor Request Case Study

## 1. Business Scenario

An employee of the fictional PC Manufacturing GmbH requires a new monitor for their workplace.

The company wants employees to create their own purchase requisitions through a self-service procurement process.

For this case study, the following fictional business rule is assumed:

- Requests with a value of up to EUR 300 do not require manager approval.
- Requests exceeding EUR 300 require approval by the responsible manager.

These thresholds are illustrative business requirements, not SAP standard rules.

## 2. Proposed Process

1. The employee identifies the need for a monitor.
2. The employee creates a self-service purchase requisition.
3. The system evaluates the applicable approval conditions.
4. If required, the responsible manager reviews the request.
5. An approved request is processed according to the company's purchasing procedure.
6. A purchase order is created and sent to the supplier.
7. Goods receipt and supplier invoice processing follow the applicable procurement process.

## 3. Business Requirements

| Requirement ID | Business Requirement |
|---|---|
| REQ-001 | Authorized employees can create their own purchase requisitions |
| REQ-002 | Requests exceeding EUR 300 require manager approval |
| REQ-003 | The requester can identify the current processing status |
| REQ-004 | Rejected requests are not processed as approved procurement requirements |
| REQ-005 | Relevant purchasing and account assignment information is available for further processing |

## 4. Proposed Test Scenarios

| Test ID | Scenario | Expected Result |
|---|---|---|
| SSR-001 | Employee submits a monitor request for EUR 250 | Request follows the process without the additional manager approval assumed in this case |
| SSR-002 | Employee submits a monitor request for EUR 450 | Request is routed for manager approval |
| SSR-003 | Manager approves a request | Request can proceed to the next defined process step |
| SSR-004 | Manager rejects a request | Request does not proceed as an approved requirement |
| SSR-005 | Unauthorized user attempts to create a request | Access is restricted according to the authorization concept |
| SSR-006 | Required account assignment information is missing | The issue is identified according to the configured validation rules |

## 5. Consultant's Perspective

The consultant must understand the business requirement before proposing a system solution. Relevant topics include requester roles, authorizations, approval responsibilities, purchasing procedures, account assignment and test coverage.

The implementation should be evaluated against the capabilities of the selected SAP S/4HANA deployment and its configuration.

**Execution status:** Conceptual case study only. No workflow has been configured or tested in a live SAP system.