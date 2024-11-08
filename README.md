

# Telangana Insights Dashboard

## Overview
The **Geographic Insights Dashboard** provides a comprehensive analysis of key metrics across districts, including document registrations, revenue, investment, and employment numbers. This dashboard is designed to assist in identifying top-performing regions and trends in geographic data.

---

## Features
### 1. **Document Registrations and Revenue Analysis**
- **Visualization:** 
  - Clustered Bar Chart: Displays districts or distribution codes with the highest and lowest document registrations and revenue.
  - Map Visualization: Highlights document registrations (size) and revenue (color intensity) for each district.
- **Insights:**
  - Identify districts with the most significant number of document registrations.
  - Pinpoint regions contributing the highest revenue.

### 2. **Investment and Employment Analysis**
- **Visualization:**
  - Clustered Column Chart: Compares investment and employment numbers across districts.
  - Treemap: Displays the contribution of each district to overall investment and employment.
  - Bubble Map: Visualizes investment levels (size) and employment distribution (color intensity).
- **Insights:**
  - Identify districts with the highest investment and employment figures.
  - Detect trends and correlations between investment and job creation.

---

## Technical Details
- **Data Sources:**
  - Data includes metrics like `documents_registered_cnt`, `documents_registered_rev`, `investment in cr`, and `number_of_employees`.
  - Aggregated by `district` or `dist_code`.
  
- **Tools Used:**
  - **Power BI Desktop**: For data transformation, DAX calculations, and visualization.
  - **Data Preparation:** Columns unpivoted for `vehicleClass` and `fuelType` to enable flexible visualization.
  - **Filters:** Top N filters applied for focused analysis.

- **Custom Measures:**
  - **Fuel Type Ratio**:
    ```DAX
    Fuel Type Ratio = DIVIDE(SUM('Table'[Registrations]), CALCULATE(SUM('Table'[Registrations]), ALL('Table'[FuelType])))
    ```
  - **Brand-New and Pre-Owned Trend Measures**:
    ```DAX
    Total Brand New = SUM('Table'[Brand_new_vehicles])
    Total Pre-Owned = SUM('Table'[Pre_owned_vehicles])
    ```

---

## Dashboard Navigation
### Pages:
1. **Document Analysis:**
   - Focused on document registrations and revenue by district.
   - Map and bar charts for geographic insights.

2. **Investment and Employment:**
   - Focused on top-performing districts in investment and employment.
   - Treemap and column charts for trends.

### Filters:
- Dynamic slicers for `district`, `fiscal_year`, `quarter`, and `vehicleClass` to customize analysis.

---

## How to Use
1. **Upload the PBIX File:**
   - Open the Power BI Desktop application and load the provided `.pbix` file.
   
2. **Explore Insights:**
   - Use interactive visuals to explore data by selecting different filters and time ranges.
   - Hover over maps and charts to view detailed metrics.

3. **Export Reports:**
   - Export insights as PDFs or share dashboards directly using Power BI Service.

---

