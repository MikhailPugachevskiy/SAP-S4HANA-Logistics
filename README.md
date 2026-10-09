# SAP S/4HANA Logistics – End-to-End Process Case Study

## Overview

This repository documents a learning project based on an SAP ERP logistics case study completed during bachelor's studies at the University of Applied Sciences Bonn-Rhein-Sieg.

The original case study focused on the production and sales of hardware products. It demonstrated how sales, material requirements planning, procurement, production, delivery, and financial processes interact within an integrated ERP system.

The goal of this repository is to refresh SAP knowledge, strengthen the understanding of end-to-end business processes, and document the learning journey toward modern SAP S/4HANA consulting.

## Business Scenario

A customer initially requests 200 PCs. The company prepares a quotation at €1,000 per PC. The customer subsequently places an order for 50 PCs.

If sufficient finished products are not available in stock, the company must plan production and procure missing components.

The process continues with delivery, goods issue, invoicing, and incoming payment.

## End-to-End Process

1. **Sales inquiry** – Record the customer's initial request.
2. **Quotation** – Prepare an offer based on the inquiry.
3. **Sales order** – Record the confirmed order for 50 PCs.
4. **Material requirements planning (MRP)** – Check stock and requirements and identify potential shortages.
5. **Procurement** – Procure missing components where necessary.
6. **Production** – Manufacture the required finished products.
7. **Delivery and goods issue** – Deliver the products and record the goods issue.
8. **Billing** – Create the customer invoice.
9. **Incoming payment** – Record the customer's payment.

## SAP Areas Involved

| SAP area | Business function |
|---|---|
| SD – Sales and Distribution | Customer inquiry, quotation, sales order, delivery, billing |
| MM – Materials Management | Procurement and inventory management |
| PP – Production Planning | Production planning and execution |
| FI – Financial Accounting | Financial processes, including incoming payments |

## Learning Objectives

- Understand integrated SAP ERP business processes.
- Explain the relationship between sales, procurement, production, and finance.
- Refresh knowledge of SAP logistics transactions.
- Compare the classic SAP ERP learning scenario with relevant SAP S/4HANA concepts.
- Develop structured process documentation and test cases.

## Project Structure

- `docs/` – Business process, master data, and SAP S/4HANA comparison.
- `test-cases/` – Process test scenarios and expected results.
- `data/` – Synthetic example data for learning purposes.

## Scope and Disclaimer

This is a personal learning project based on a university case study. It is not a live SAP implementation and does not claim that the original exercises were performed in SAP S/4HANA.

The SAP S/4HANA comparison will be documented separately as part of the learning process.

## Author

This project supports professional development toward a Junior SAP Consultant role, with a focus on logistics processes, process analysis, and SAP S/4HANA.