# Material Requirements Planning (MRP) – Process Case Study

## 1. Purpose

This document explains how Material Requirements Planning (MRP) connects sales demand, production planning and procurement.

The case study builds on the classic SAP ERP hardware production scenario covered in my university coursework.

This is a learning document. No execution in a live SAP S/4HANA system is claimed.

## 2. Business Scenario

A customer orders 50 PCs. The company must determine whether sufficient finished products and components are available.

If additional PCs must be produced, the company needs to check whether the required components are available or must be procured.

For illustration, assume each PC requires one housing and one hard drive. The company has 50 housings but only 20 hard drives available.

Under these simplified assumptions, 30 additional hard drives are required.

## 3. MRP Objectives

MRP helps determine:

- Which materials are required
- What quantities are required
- When the materials are needed
- Whether procurement or production proposals are necessary

The result depends on the relevant requirements, stock situation, master data and planning parameters.

## 4. Classic SAP ERP Exercise

The university exercise used the following transactions:

| Transaction | Purpose in the exercise |
|---|---|
| MD02 | Execute material requirements planning |
| MD04 | Review the stock/requirements situation |

The planning process can identify material shortages and create planning proposals.

In the documented hardware case, planned orders and purchase requisitions were reviewed as part of the production and procurement process.

These transaction codes describe the classic SAP ERP learning environment and should not automatically be treated as the recommended interface for every SAP S/4HANA system.

## 5. Process Flow

1. A customer order creates demand for finished products.
2. Production requirements are reviewed.
3. MRP evaluates material requirements and the supply situation.
4. Planning proposals are reviewed.
5. Missing externally procured components can be procured.
6. Missing in-house-produced materials can require production planning.
7. Goods receipts and production activities update the relevant supply situation.

The exact sequence depends on the material settings, available stock, planning parameters and business scenario.

## 6. Integration with Other SAP Areas

| Area | Contribution |
|---|---|
| Sales and Distribution (SD) | Customer demand |
| Production Planning (PP) | Production requirements and orders |
| Materials Management (MM) | Procurement and inventory management |
| MRP | Material requirement and supply planning |

## 7. Test Scenario

**Test ID:** MRP-001

**Status:** Designed – execution not performed

**Preconditions:**

- A material master exists.
- Relevant planning data is maintained.
- Requirements and stock quantities are available for review.

**Test steps:**

1. Review the stock/requirements situation.
2. Execute the applicable planning run in the training environment.
3. Review the resulting planning proposals.
4. Check whether shortages are addressed by suitable procurement or production proposals.

**Expected result:**

The planning results reflect the relevant requirements and supply situation, and any material shortages can be investigated through the resulting proposals.

## 8. Learning Objectives

- Explain the purpose of MRP.
- Distinguish planning from reviewing the stock/requirements situation.
- Understand how sales demand can affect production and procurement.
- Explain the relationship between SD, PP and MM.
- Distinguish documented classic ERP experience from future S/4HANA practical learning.