# 🌍 Sustainability & Carbon Footprint Dashboard (Power BI)

## 📌 Project Overview
This Power BI dashboard helps organizations **track, analyze, and reduce their carbon footprint**.  
It provides insights into **CO₂ emissions, renewable energy usage, recycling impact, and cost savings** — all in one place.  

## ✨ Key Features
- 📊 **CO₂ Emissions Trend** (with YoY comparison & forecasts)  
- ⚡ **Renewable vs Non-Renewable Energy Split**  
- 🔄 **Recycling & Waste Reduction Metrics**  
- 💰 **Sustainability Cost Savings Tracker**  
- 🎛️ Interactive **filters for Year, Business Unit, and Energy Source**  

## 🗂️ Dataset
Sample dataset: `sustainability_sample.csv`  
- `Date` → Daily/Monthly records  
- `BusinessUnit` → Dept/Plant/Location  
- `EnergySource` → Renewable / Non-renewable  
- `CO2 (tons)` → Emissions  
- `Recycled (tons)` → Waste recycled  
- `CostSavings ($)` → Estimated savings  

## 🚀 Visual Layout
1. **Top KPIs (Cards)** → Total CO₂, Renewable %, Recycling %, Cost Savings  
2. **Line Chart** → Monthly CO₂ Trend with YoY comparison  
3. **Donut Chart** → Energy source distribution  
4. **Bar Chart** → CO₂ by Business Unit  
5. **Slicer Filters** → Year, Month, Business Unit  

## 🎨 Theme
Applied a custom **eco-theme** (green, blue, earthy tones) for a clean sustainability look.  

## 📷 Dashboard Preview

<img width="643" height="362" alt="image" src="https://github.com/user-attachments/assets/252eb49c-204d-41c1-8891-9d1fe7c396bc" />


## ⚡ Getting Started
1. Open **Power BI Desktop**  
2. Load `sustainability_sample.csv`  
3. Create a **Date Table** with DAX:  
   ```DAX
   DateTable = CALENDARAUTO()
4. Build measures like:

Total CO2 (tons) = SUM(Sustainability[CO2 (tons)])
CO2 Last Year = CALCULATE([Total CO2 (tons)], SAMEPERIODLASTYEAR(DateTable[Date]))

5. Apply eco_theme.json under View → Themes → Browse


---

## 3️⃣ PBIX Build Order 🛠️

Here’s how to **arrange visuals step by step**:

### 🔹 Page Layout (Dashboard Canvas)
- Background: light eco green/white (use imported theme).
- Grid: 3 rows (KPIs, Main charts, Detail charts).

---

### 🔸 Row 1 → **KPI Cards (top row)**
- `Total CO2 (tons)` → Card
- `Renewable %` = DIVIDE(SUM(Renewable), SUM(Total Energy)) → Card
- `Recycled (tons)` → Card
- `Cost Savings ($)` → Card

---

### 🔸 Row 2 → **Main Insights**
- Left: **Line Chart**  
  - X = `DateTable[Date]`  
  - Y = `[Total CO2 (tons)]`  
  - Add `[CO2 Last Year]` for comparison  
- Right: **Donut Chart**  
  - Values = `Total CO2 (tons)`  
  - Legend = `EnergySource`  

---

### 🔸 Row 3 → **Breakdowns & Filters**
- Left: **Bar Chart**  
  - Axis = `BusinessUnit`  
  - Values = `[Total CO2 (tons)]`  
- Right: **Slicer**  
  - Field = `DateTable[YearMonth]`  
  - Format = Dropdown (to save space)  

---

👉 Once done, you’ll have a **professional, recruiter-friendly, eco-themed sustainability dashboard** 🌍.

## Author: Atrima

