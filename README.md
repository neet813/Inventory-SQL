# Inventory Optimization Project (v1.0)

**Author:** Navneet Kaur  
**Goal:** Demonstrate a complete SQL-first inventory optimization pipeline with Python, showing shortages, overstock, and transfer recommendations.

---

## 🔹 Problem

Warehouses often face **overstock or stockouts**, which can:

- Waste money on excess inventory  
- Take up valuable warehouse space  
- Delay customer orders if stock is insufficient  

This project simulates a multi-warehouse inventory system and **automates stock balancing**.

---

## 🔹 Solution

I built a **SQL-first Python pipeline** that:

1. Loads inventory data from CSV  
2. Converts it into a **long table** (product × warehouse)  
3. Calculates **target stock per warehouse**  
4. Computes **shortages and surplus**  
5. Generates **transfer recommendations** between warehouses:
   - `DC_MAIN` → main warehouse fulfilling orders  
   - `DC_INTERNAL` → first source for transfers  
   - `SUPPLIER_A` and `SUPPLIER_B` → external warehouses if internal stock insufficient  

The solution also calculates **overstock cost** and creates **visualizations** for decision-making.

---

## 🔹 Features / Skills Demonstrated

- **Python**: pandas, numpy, matplotlib  
- **SQL**: SQLite for data transformation  
- **Inventory logic**: shortages, surpluses, transfers  
- **Visualization**: bar charts, pie charts, stacked bar charts  
- **Data handling**: CSV input/output, clean pipeline  

---

## 🔹 Outputs

All outputs are stored in `outputs/` folder:

- `stock_position.csv` → product-level shortage/surplus  
- `transfer_recommendations.csv` → suggested stock movements  
- `overstock_report.csv` → surplus quantity and value  

### Example Output (Sample)

| Product Name | Warehouse | Current Stock | Shortage | Surplus | Transfer Recommendation |
|--------------|----------|---------------|----------|---------|------------------------|
| Product 1    | DC_MAIN  | 55            | -55      | 55      | DC_INTERNAL → DC_MAIN: 55 units |
| Product 6    | DC_INTERNAL | 159        | 0        | 159     | SUPPLIER_A → DC_INTERNAL: 100 units |

*(Replace this table with actual sample from your outputs)*

---

## 🔹 Visualizations

*(Add screenshots from Colab here)*

**1️⃣ Total Overstock Value per Warehouse**  
Bar chart showing how much money is tied up in each warehouse.

**2️⃣ Overstock Distribution by Warehouse**  
Pie chart showing percentage of overstock per warehouse.

**3️⃣ Top 10 Products Overstock by Warehouse**  
Stacked bar chart highlighting the most expensive surplus items.

---

## 🔹 How to Run

1. Clone the repository.  
2. Install dependencies:

```bash
pip install pandas numpy matplotlib

### 1️⃣ Data Generation

![Data Generation](screenshots/01_data_generation.png)

---

### 2️⃣ SQL Long Table Creation

![SQL Long Table](screenshots/02_sql_long_table.png)

---

### 3️⃣ Stock Position Table

![Stock Position](screenshots/03_stock_position.png)

---

### 4️⃣ Transfer Recommendations

![Transfer Recommendations](screenshots/04_transfer_recommendations.png)

---

### 5️⃣ Overstock Charts

![Overstock Charts](screenshots/05_overstock_charts.png)
