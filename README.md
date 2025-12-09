# 📦 Inventory Optimization System - V1

> Automated warehouse inventory management with Python & SQL

---

## 🔒 Data Privacy Notice

⚠️ **This project uses simulated data for demonstration purposes.**

All data is synthetic to protect company confidentiality. The problem and solution are real, but product names, stock quantities, and financial figures are made up.

---

## 💡 The Problem

Every morning, someone spent 30-60 minutes:
- Checking inventory levels across 4 warehouses  
- Identifying what needs to be transferred
- Coordinating with other locations via email/calls

This was:
- ⏰ Time-consuming (130-260 hours/year)
- 😓 Repetitive and manual
- ❌ Prone to errors
- 📉 Reactive instead of proactive

---

## ✅ The Solution

I rebuilt this entire workflow in **Python & SQL**:

**Before:** 30-60 minutes every morning  
**After:** 5 seconds ⚡

### Features:
- Automated stock level analysis
- Transfer recommendations between warehouses
- Overstock and shortage identification
- Cost impact visualization
- No more manual coordination needed

---

## 💰 Business Impact

- **Time saved:** 130-260 hours/year
- **Value:** £2,300-4,500/year in productivity gains
- **Eliminated:** Manual coordination errors
- **Result:** Person can start day productively, not stuck in spreadsheets

---

## 🛠️ Technical Stack

- **Python 3.8+** - Core programming
- **Pandas** - Data analysis
- **SQLite** - Database
- **Matplotlib** - Visualizations
- **SQL** - Complex queries and transformations

---

## 🚀 How It Works

1. **Data Import:** CSV files → SQLite database
2. **Analysis:** Calculate target vs actual stock levels
3. **Recommendations:** Identify optimal transfers
4. **Visualization:** Charts showing overstock/shortage
5. **Reports:** Ready-to-use transfer lists

---

## 📊 Warehouse Logic

| Warehouse | Target Stock | Purpose |
|-----------|--------------|---------|
| DC_MAIN | 0 weeks | Customer-facing, just-in-time |
| DC_INTERNAL | 4 weeks | Regional hub, buffer stock |
| SUPPLIER_A | 8 weeks | Long-term storage |
| SUPPLIER_B | 8 weeks | Long-term storage |

**Transfer hierarchy:**  
SUPPLIER → DC_INTERNAL → DC_MAIN

---

## 📁 Project Files

```
inventory-optimization-v1/
├── README.md                    # This file
├── requirements.txt             # Python dependencies
├── inventory_analysis.ipynb     # Main analysis notebook
├── sample_data/
│   └── inventory_sample.csv     # Synthetic data
└── outputs/
    ├── stock_position.csv       # Analysis results
    └── transfer_recommendations.csv
```

---

# Install dependencies
pip install -r requirements.txt

# Open the notebook
jupyter notebook inventory_analysis.ipynb
```

---

📈 Key Results (from synthetic data)

50 products analyzed

Overstock value: ~£145k

Transfers recommended: 90+

Warehouse with highest overstock: DC_INTERNAL

Stockouts prevented at DC_MAIN: Yes — 100%

(Values based on generated mock data)

---

## 🗺️ Roadmap

### V1 (Current) ✅
- Inventory analysis
- Transfer recommendations
- Cost visualization

### V2 (Planned) 🔄
- ML demand forecasting (ARIMA/Prophet)
- Automated morning email alerts
- Enhanced transfer optimization
- Lead time considerations

### V3 (Future) 🔮
- Real-time web dashboard
- ERP system integration
- Multi-objective optimization

---

## 🧠 What I Learned

**Technical:**
- SQL query optimization (CTEs, JOINs)
- Python data pipeline development
- Automating repetitive workflows
- Data visualization best practices

**Business:**
- Understanding warehouse operations
- ROI calculation for automation projects
- Balancing simplicity vs. complexity
- Importance of data privacy

**Development:**
- Used AI tools (ChatGPT, Claude) to accelerate coding
- Iterative approach: V1 simple, V2 adds ML
- Importance of documentation

---

## 📝 License

MIT License - See LICENSE file

---

## 📧 Contact

**NAVNEET KAUR**  
📧 Email: neetkr.2525@example.com  
💼 LinkedIn: https://www.linkedin.com/in/navneet-kaur-analyst/
🐙 GitHub: https://github.com/neet813

---

## 🙏 Acknowledgments

- Problem based on real warehouse operations
- **All data is synthetic** to protect confidentiality
- Solution applicable to any multi-warehouse system

---

**⭐ If you find this useful, please star the repository!**

*Last updated: December 2025*
