# Inventory Optimization Project (v1.0)

**Author:** Your Name  
**Goal:** Manage warehouse stock efficiently and show overstocked items in a simple visual way.

## Description
This project simulates an inventory system with multiple warehouses:

- `DC_MAIN` → Main warehouse (fulfills orders)  
- `DC_INTERNAL` → Internal backup warehouse  
- `SUPPLIER_A` → External warehouse 1  
- `SUPPLIER_B` → External warehouse 2  

**Logic:**
1. If DC_MAIN has a shortage → pull from DC_INTERNAL first.  
2. If DC_INTERNAL has less than 4 weeks of stock → pull from SUPPLIER_A, then SUPPLIER_B.  
3. DC_MAIN never sends stock out.

## Features
- SQL-based inventory processing (SQLite in Python)  
- Generates reports:
  - Stock positions  
  - Transfer recommendations  
  - Overstock report (quantity and value)  
- Visualizations:
  - Overstock per warehouse  
  - Top 10 expensive overstocked products  
  - Pie chart showing warehouse overstock distribution  

## How to Run
1. Install dependencies:

```bash
pip install pandas numpy matplotlib

