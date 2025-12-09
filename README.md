# 📦 Inventory Optimization & Transfer Recommendation System

> **V1: Analysis & Insights** | A data-driven approach to warehouse inventory management


**SAMPLE DATA
<img width="808" height="209" alt="image" src="https://github.com/user-attachments/assets/e89fa86a-17b5-4872-8287-3a707d0c52d8" />


**TRANSFER RECOMMENDATIONS : (MAIN WAREHOUSE : DC_MAIN , TRANSFER FROM 3 WAREHOUSE , [DC_INTERNAL ,SUPPLIER_A,SUPPLIER_B ])
<img width="678" height="385" alt="image" src="https://github.com/user-attachments/assets/ce670887-b8d8-44ff-a3a7-478214aae672" />

**
<img width="674" height="369" alt="image" src="https://github.com/user-attachments/assets/75615b09-888a-4e6a-bdf9-de4bea78062f" />

<img width="1005" height="588" alt="image" src="https://github.com/user-attachments/assets/461cf6e8-3d83-4ad1-8bc0-409ca193211b" />

---

## 🎯 **Project Overview**

A warehouse inventory optimization system that identifies overstock, shortages, and provides actionable transfer recommendations to reduce carrying costs and prevent stockouts.

**Current Version (V1):** Analysis & Reporting  
**Next Version (V2):** Automated recommendations with ML forecasting & email alerts

---

## 💡 **The Problem**

### Origin Story:
In our warehouse operations, **someone had to do this EVERY SINGLE MORNING:**
1. ☕ Come into work
2. 📊 Open Google Sheets
3. 🔍 Check stock levels across 4 warehouses
4. 🤔 Identify which products need transfers
5. 📧 Send messages to other warehouses about what they need
6. ⏰ **30-60 minutes EVERY DAY** before they could do anything else

This daily routine was:
- 😓 **Repetitive & tedious** - same process every morning
- ⏰ **Time-consuming** - 30-60 min/day = 130-260 hours/year
- 🐌 **Manual coordination** - emails/calls to multiple warehouses
- 📉 **No historical tracking** - decisions based on today's snapshot only
- ❌ **Error-prone** - easy to miss shortages when rushed
- 💸 **Reactive** - only caught problems when they became critical

### Real-World Example:
> "DC_MAIN is running low on Product X? Let me check... DC_INTERNAL has surplus. I'll send them an email to transfer 50 units. Oh wait, SUPPLIER_A has even more. Better coordinate that instead..."
> 
> **Every. Single. Morning.**

### Why I Rebuilt It in Python/SQL:
I saw this daily struggle and thought: *"This entire workflow can be automated."*

**The Solution:**
- ⚡ **Instant analysis** - what took 30-60 minutes now takes 5 seconds
- 🤖 **Automated recommendations** - system calculates optimal transfers
- 📧 **Auto-generated reports** - ready-to-send transfer list (V2: automated emails)
- 📊 **Historical tracking** - see trends, not just today's snapshot
- ✅ **Error-free** - consistent logic, no human oversight
- 🔮 **Proactive** - identifies problems before they become critical

### Business Impact:
- **Freed up 130-260 hours/year** (daily morning routine eliminated)
- **Value: £2,275-4,550/year** in time savings alone
- Identified **£XXXk in overstock** across 4 warehouses
- Recommended **XX optimal transfers** automatically
- **Person now starts day productively** instead of doing spreadsheet analysis
- **Faster decisions** - from daily manual checks to instant insights
- **V2 will add:** Automated morning email with transfer recommendations (zero manual work)

---

## 🚀 **Key Features (V1)**

### ✅ **What's Implemented:**
1. **Inventory Analysis**
   - Multi-warehouse stock level tracking
   - Target vs. actual stock comparison
   - Shortage and surplus identification

2. **Transfer Recommendations**
   - Smart warehouse hierarchy logic
   - Optimal unit movement calculations
   - Cost impact analysis

3. **Business Insights**
   - Overstock cost analysis (£k per warehouse)
   - Visual dashboards (charts & distributions)
   - Top 10 products by overstock value

4. **Data Pipeline**
   - CSV → SQLite database
   - SQL-based transformations
   - Automated reporting

---

## 🏗️ **Technical Architecture**

```
┌─────────────────┐
│  Raw CSV Data   │
└────────┬────────┘
         │
         ↓
┌─────────────────┐
│ SQLite Database │  ← Data ingestion & transformation
└────────┬────────┘
         │
         ↓
┌─────────────────┐
│  SQL Analytics  │  ← Business logic (shortages, surpluses, transfers)
└────────┬────────┘
         │
         ↓
┌─────────────────┐
│ Pandas Analysis │  ← Cost calculations & aggregations
└────────┬────────┘
         │
         ↓
┌─────────────────┐
│ Visualizations  │  ← Charts & reports (Matplotlib)
└─────────────────┘
```

---

## 📊 **Warehouse Logic**

The system uses target stock levels based on warehouse type:

| Warehouse Type | Target Weeks | Purpose |
|---------------|--------------|---------|
| **DC_MAIN** (Customer-facing) | 0 weeks | Just-in-time delivery to customers |
| **DC_INTERNAL** (Regional hub) | 4 weeks | Buffer for DC_MAIN + regional orders |
| **SUPPLIER_A** (Vendor warehouse) | 8 weeks | Long-term storage + bulk inventory |
| **SUPPLIER_B** (Vendor warehouse) | 8 weeks | Long-term storage + bulk inventory |

### Transfer Hierarchy:
```
SUPPLIER_A/B → DC_INTERNAL → DC_MAIN
(8 weeks)      (4 weeks)     (0 weeks)
```

---

## 🛠️ **Technologies Used**

- **Python 3.8+** - Core programming language
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computations
- **SQLite** - Lightweight database for data storage
- **Matplotlib** - Data visualization
- **SQL** - Complex queries (CTEs, JOINs, aggregations)

---

## 📁 **Project Structure**

```
inventory-optimization-v1/
│
├── README.md                          # This file
├── requirements.txt                   # Python dependencies
├── inventory_analysis.ipynb           # Main Jupyter notebook
│
├── sample_data/
│   └── inventory_sample.csv           # Generated sample data (50 products)
│
├── sql/
│   └── (SQL transformations stored in notebook)
│
├── outputs/
│   ├── inventory.db                   # SQLite database
│   ├── stock_position.csv             # Analysis results
│   ├── transfer_recommendations.csv   # Transfer suggestions
│   └── charts/                        # Generated visualizations
│
└── docs/
    └── ROADMAP.md                     # V2 features & timeline
```

---

## 🚀 **Getting Started**

### Prerequisites:
```bash
Python 3.8+
pip install pandas numpy matplotlib
```

### Installation:
```bash
# Clone the repository
git clone https://github.com/yourusername/inventory-optimization.git
cd inventory-optimization

# Install dependencies
pip install -r requirements.txt

# Run the notebook
jupyter notebook inventory_analysis.ipynb
```

### Quick Start:
```python
# The notebook runs end-to-end:
# 1. Generates sample data (50 products, 4 warehouses)
# 2. Creates SQLite database
# 3. Calculates shortages/surpluses
# 4. Generates transfer recommendations
# 5. Produces visualizations
```

---

## 📈 **Sample Results**

### Overstock Analysis:
- **Total overstock value:** £XXXk across 4 warehouses
- **Highest overstock:** DC_INTERNAL (XX%)
- **Top product:** Product X (£XXk overstock)

### Transfer Recommendations:
- **XX total transfers** recommended
- **Average transfer size:** XX units
- **Estimated savings:** £XXk in carrying costs

### Key Insights:
1. SUPPLIER warehouses have 60% of total overstock
2. DC_MAIN frequently has shortages (as designed)
3. Product X has highest surplus-to-shortage ratio

---

## 🗺️ **Roadmap: V1 → V2**

### ✅ **V1 (Current) - Analysis & Insights**
- [x] Data pipeline (CSV → SQLite)
- [x] Stock position analysis
- [x] Transfer recommendations
- [x] Cost impact visualization
- [x] Manual report generation

### 🔄 **V2 (In Progress) - Automation & ML**
- [ ] **Machine Learning Forecasting**
  - ARIMA/Prophet for demand prediction
  - Seasonality detection
  - Anomaly detection (unusual demand spikes)
  
- [ ] **Automated Alert System**
  - Email alerts for critical shortages
  - Daily/weekly summary reports
  - Threshold-based notifications
  
- [ ] **Enhanced Recommendations**
  - Multi-step transfer optimization
  - Cost-benefit analysis per transfer
  - Lead time considerations
  
- [ ] **Web Dashboard** (Optional)
  - Real-time inventory visibility
  - Interactive charts (Plotly/Dash)
  - One-click transfer approval

### 🔮 **V3 (Future) - Advanced Features**
- Real-time integration with ERP systems
- Multi-objective optimization (cost + service level)
- Supplier lead time variability modeling
- What-if scenario analysis

---

## 🛤️ **Development Journey**

### Phase 0: Google Sheets (Original)
- ✅ Manual process EVERY MORNING (30-60 min/day)
- ✅ Validated business logic with real coordination workflow
- ✅ Understood warehouse operations intimately
- ❌ **Daily time sink** before any real work could start
- ❌ Manual emails/calls to coordinate transfers
- ❌ Reactive - only caught problems when critical
- ❌ No historical tracking or trend analysis
- ❌ Prone to human error when rushed

### Phase 1: Python/SQL Migration (V1 - Current)
- ✅ **Automated the ENTIRE daily routine** (30-60 min → 5 seconds)
- ✅ Instant transfer recommendations
- ✅ Eliminated daily manual coordination
- ✅ Professional visualizations for management
- ✅ Historical tracking and trend analysis
- ✅ Scalable to 1000+ products
- 💰 **Impact:** Freed up 130-260 hours/year (£2,275-4,550 value)
- 🎯 **Real benefit:** Person can start day productively, not stuck in spreadsheets
- 📝 **Learning:** Used AI coding assistants but validated every line

### Phase 2: ML & Automation (V2 - In Progress)
- 🔄 **Automated morning emails** - transfer recommendations sent automatically
- 🔄 Adding demand forecasting (predict tomorrow's needs)
- 🔄 Alert system for critical shortages
- 🔄 Enhanced transfer optimization with lead times
- 🔄 Performance monitoring
- 🎯 **Goal:** Zero manual morning work - wake up to ready recommendations

### Phase 3: Production System (V3 - Future)
- 🔮 Web dashboard
- 🔮 Real-time ERP integration
- 🔮 Multi-objective optimization

---

## 🧠 **What I Learned**

### Technical Skills:
- **Python → SQL migration:** Transformed spreadsheet formulas into efficient SQL queries
- **Database design:** Wide-to-long format transformation for scalability
- **Performance optimization:** Reduced analysis time from minutes to seconds
- **Data visualization:** Created professional charts to replace manual Excel graphs

### Development Process:
- **Started with Google Sheets** - validated business logic with real data
- **Used AI tools** (ChatGPT/Claude) to accelerate coding - but I understand and can modify every line
- **Iterative approach** - built V1 first (analysis), planning V2 (ML + automation)
- **Real-world testing** - validated results against original spreadsheet calculations

### Challenges Overcome:
1. **Initial approach:** Tried to replicate every spreadsheet formula → realized SQL could do it better
2. **Data structure:** Learned that long format (warehouse as a row) is better than wide format (warehouse as column) for scalability
3. **Transfer logic:** Had to implement warehouse hierarchy to prevent invalid transfers (e.g., SUPPLIER → DC_MAIN directly)
4. **Cost calculation:** Added unit costs to quantify business impact in £k

### Business Understanding:
- Different warehouses serve different purposes (buffer vs. customer-facing)
- Overstock has real financial impact (carrying costs, capital tied up)
- **Speed matters:** 2 hours/week manual work = 100+ hours/year saved
- Simple automation beats complex manual processes

---

## 📊 **Key Metrics**

| Metric | Value | Impact |
|--------|-------|--------|
| Products Analyzed | 50 | Representative sample |
| Warehouses | 4 | Multi-tier supply chain |
| Total Overstock | £XXXk | Capital tied up |
| Transfers Recommended | XX | Operational efficiency |
| Potential Savings | XX% | Cost reduction |

---

## 🤝 **Contributing**

This is a portfolio project, but feedback and suggestions are welcome!

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Commit your changes
4. Push to the branch
5. Open a Pull Request

---

## 📝 **License**

This project is open source and available under the MIT License.

---

## 📧 **Contact**

**[Your Name]**  
📧 Email: neetkr.2525@gmail.com  
💼 LinkedIn: [(https://www.linkedin.com/in/navneet-kaur-analyst/)]
🐙 GitHub: https://github.com/neet813

---

## 🙏 **Acknowledgments**

- Inspired by real-world warehouse management challenges
- Data structure based on typical ERP system outputs
- Business logic validated with supply chain professionals

---

## 📌 **Version History**

- **V1.0 (Current)** - Initial release with analysis & reporting
- **V2.0 (Planned)** - ML forecasting + email automation
- **V3.0 (Future)** - Real-time dashboard + ERP integration

---

**⭐ If you find this project useful, please consider giving it a star!**

---

*Last updated: December 2024*
