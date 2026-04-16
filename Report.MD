# Maritime Terminal Operations Analysis for Global Maritime Solutions Company
**Reducing Cargo Movement Times & Identifying Bottlenecks**

![My Image](https://github.com/R887645/-Maritime-Terminal-Operations-Analysis/blob/main/Maritime%20Terminal%20Operation%20Analysis%20.png?raw=true)

### Project Description
I participated in this month of April's Onyx Data Challenge, where I stepped into the role of a Senior Operations Analyst at the company to analyze global maritime terminal operations to uncover inefficiencies, bottlenecks, and disruption impacts. Using cargo movement data across hubs, terminals, and vessel categories, the dashboard helps leadership reduce average movement times by 15% and optimize terminal allocation.

---

## Business Problem / Objective
Global Maritime Solutions wants to move from raw cargo and terminal data to actionable insights.  

Leadership needs clear visibility into:  
- How container volumes and movement duration evolve, including disruption impacts and recovery patterns following the **2021 Suez Canal incident**  
- Which regional hubs (EMEA, APAC, AMER, LATAM) and individual terminals contribute most to overall cargo throughput and operational delays  
- What differentiates high‑performing vs underperforming terminals within the same region  
- Whether terminal utilization levels are correlated with longer movement times and potential infrastructure bottlenecks  

This project was designed to answer the core question:  
**“How can the company reduce cargo movement times by 15% and optimize terminal allocation?”**

---

## Dataset Overview
- **Data Source:** Maritime Terminal Operations dataset (Onyx Data Challenge)  
- **Time Period Covered:** 2021 – 2024  
- **Volume:** 15K cargo movements, 8M containers, 50 active terminals  
- **Format:** CSV/Excel files  
- **Key Columns:**  
  - terminal_name, regional_hub  
  - container_count, move_duration, throughput_rate  
  - vessel_category, vessel_name  
  - date_id, shift (day/night)  
  - Suez Period (pre/post disruption)  

---

## Tools Used
- **Power Query** – Data cleaning and transformation  
- **Power BI** – Data modeling, dashboard design, visualization, Wireframing dashboard layout, and storytelling flow  

---

## Data Cleaning & Preparation
- Removed duplicates and standardized terminal, vessel, and hub naming  
- Converted numeric fields (container_count, move_duration) to proper data types  
- Built dimensional tables (`dim_terminal`, `dim_vessel`, `dim_time`, `Calendar`) linked to `fact_cargo_movements`  
- Created calculated fields for utilization %, bottleneck tiers, and efficiency scores  

**Calendar Table Created for Time Intelligence:**  
- Date, Year, Month, MonthNum, Quarter, HalfMonth  

![My Image](https://github.com/R887645/-Maritime-Terminal-Operations-Analysis/blob/main/Terminal_Datacleaning.png?raw=true)

---

## Data Modelling
- Star schema with `fact_cargo_movements` at the center  
- Relationships established with terminal, vessel, and time dimensions  
- Calendar table enabled rolling averages and disruption period analysis  

![My Image](https://github.com/R887645/-Maritime-Terminal-Operations-Analysis/blob/main/Maritime%20Onyx_Data%20Modelling.png?raw=true)

---

## Calculated Measures (DAX)
- **Terminal Utilization %**  
- **Avg Utilization**  
- **Recovery Months (Suez)**  
- **Efficiency Score**  
- **Total Cargo Movements, Total Containers, Avg Move Duration**  
- **MoM Container Volume Change, YoY Growth**  
- **Added some calculation columns, like Bottleneck Tier Classification, and Suez Period**, and lots more, as I encountered the challenge of not being able to use the measures as legend, so I used calculated columns instead to fix it.

![My Image](https://github.com/R887645/-Maritime-Terminal-Operations-Analysis/blob/main/Terminal_dax%202.png?raw=true)

![My Image](https://github.com/R887645/-Maritime-Terminal-Operations-Analysis/blob/main/Terminal_Calc%20column.png?raw=true)

---

## Key Questions & Analysis
- How did container volumes and movement duration evolve during and after the Suez disruption?  
- Which hubs and terminals drive throughput vs delays?  
- What differentiates efficient vs bottleneck terminals?  
- Is high utilization correlated with longer movement times?  
- How close are we to the 15% reduction target?  

---

## Key Insights
- **Suez Impact:** Avg duration spiked 4.26% post‑blockage; recovery took several months.  
- **Regional Drivers:** EMEA leads with 5.7K movements, but APAC outperforms on throughput rate at 501.35, proving volume and efficiency are not the same thing. 
- **Terminal Bottlenecks:** 42 terminals operated above 85% utilization, creating pressure.  
- **Efficiency Gaps:** Bottom 5 terminals averaged throughput rates between 471-481, with Matthew Jones terminal at the lowest at 471
- **Shift Balance:** Day vs night split was nearly even, but certain hubs leaned heavily on night shifts.  
- **Target Progress:** Current avg duration = 20.88 days vs target 17.75 (still above goal).  
- LATAM and APAC hubs consistently performed below the global average movement duration, making them the most time-efficient regions despite lower volumes

![My Image](https://github.com/R887645/-Maritime-Terminal-Operations-Analysis/blob/main/Screenshot%202026-04-16%20065605.png?raw=true)

![My Image](https://github.com/R887645/-Maritime-Terminal-Operations-Analysis/blob/main/Screenshot%202026-04-16%20065704.png?raw=true)

![My Image](https://github.com/R887645/-Maritime-Terminal-Operations-Analysis/blob/main/Screenshot%202026-04-16%20065906.png?raw=true)

![My Image](https://github.com/R887645/-Maritime-Terminal-Operations-Analysis/blob/main/Screenshot%202026-04-16%20072810.png?raw=true)

---

## Recommendations
- Prioritize interventions at bottleneck terminals above 85% utilization.  
- Investigate EMEA hub delays despite high throughput.  
- Optimize allocation across day/night shifts to balance workloads.  
- Strengthen resilience planning for future disruptions.  
- Focus efficiency programs on the bottom 5 terminals to close the gap toward the 15% reduction target.  

---

## Dashboard / Visualization
The Power BI Report contains **4 main pages**:

1. **Global Cargo Performance Overview**  
   - KPIs: Total Movements, Total Containers, Avg Duration, Target Gauge  
   - Trends: Avg Duration line chart, Container split by vessel category, Movements by hub  

2. **Disruption Impact (Suez 2021)**  
   - KPIs: Movements Lost, Container Volume Change, Duration Spike, Recovery Months  
   - Charts: Monthly trend with disruption marker, MoM container change, Recovery tracker  

3. **Regional Hub & Terminal Analysis**  
   - KPIs: Active Terminals, Throughput Rate  
   - Charts: Scatter plot (Movements vs Duration), Bottom 5 terminals, Hub comparison bar chart, Shift split  

4. **Efficiency & Bottleneck Watch**  
   - KPIs: Avg Utilization %, Terminals above 85%, Bottleneck Pressure Score, Efficiency Score  
   - Charts: Scatter plot (Utilization vs Duration, Bottleneck Tier legend), Efficiency rankings, Day vs Night split  

---

## How This Project Sharpened My Skills
- Advanced Power BI dashboard design and storytelling  
- Creating dynamic DAX measures for utilization, bottlenecks, and recovery analysis  
- Implementing interactive filters and slicers for hub/terminal drilldowns  
- Translating operational data into actionable leadership insights  
- Structuring dashboards to tell a clear narrative: **Overview → Disruption → Hubs → Bottlenecks**

---

## Challenges Faced
- Designing bottleneck tier logic with median reference lines  
- Configuring disruption recovery calculations (Recovery Months)  
- Balancing visual clarity vs detail (removing duplicate scatter plots, replacing raw tables with ranked charts)  
- DAX measures cannot be used as legends or slicers in Power BI, resolved by creating calculated columns for Bottleneck Tier Classification and Suez Period instead

---

## Conclusion
This project transformed raw maritime operations data into actionable insights. The analysis helped leadership:  
- Understand disruption impacts and recovery timelines  
- Identify regional hub drivers and terminal bottlenecks  
- Track progress toward the 15% reduction target  
- Optimize terminal allocation for efficiency gains  

---

## Limitations
- The dataset does not include external factors (weather, geopolitical risks, competitor activity).  
- Marketing spend and customer demand data were not captured.  
- Including predictive models could strengthen future planning.  

---

👋 I am **Abdul-Azeez Rofiah Kehinde**, Let's connect [LinkedIn](https://www.linkedin.com/in/rofiah-abdul-azeez/) 

You can also read my article on Medium](https://medium.com/p/a916172af208?postPublishedType=initial)
