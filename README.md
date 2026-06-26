# 🚦 Accident Severity Prediction & Risk Analytics

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow?logo=powerbi)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

A comprehensive end-to-end data science project that analyzes road traffic accident (RTA) data to identify key risk factors, predict accident severity using machine learning, and deliver actionable insights for road safety improvement — paired with an interactive Power BI dashboard.

---

## 📌 Table of Contents

- [Project Overview](#project-overview)
- [Problem Statement](#problem-statement)
- [Objectives](#objectives)
- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Analysis Phases](#analysis-phases)
- [Key Insights](#key-insights)
- [Strategic Recommendations](#strategic-recommendations)
- [Tools & Technologies](#tools--technologies)
- [How to Run](#how-to-run)

---

## 📖 Project Overview

Road Traffic Accidents (RTAs) are a leading cause of death and disability worldwide, resulting in significant social and economic losses. This project leverages **Exploratory Data Analysis (EDA)**, **advanced visualizations**, and **machine learning** to uncover the key driver, vehicle, road, and environmental factors that influence accident severity.

The project is delivered in two complementary formats:
- **Jupyter Notebook** — detailed EDA, statistical analysis, and business insights across 12 structured phases
- **Power BI Dashboard** — interactive executive-level road safety monitoring dashboard

This project also lays the foundation for advanced predictive modeling — the cleaned features and risk segments created during EDA are directly usable for training classification models such as Random Forest, XGBoost, or LightGBM to predict accident severity. Future scope includes geospatial hotspot analysis, real-time risk monitoring, and explainable AI (SHAP/LIME) for transparent, data-driven road safety decisions.

---

## ❗ Problem Statement

Road Traffic Accidents (RTAs) are a major public safety concern, resulting in injuries, fatalities, property damage, and economic losses. Understanding the factors contributing to accident severity is essential for improving road safety and reducing accident-related risks.

This project analyzes historical accident records to identify the key factors influencing severity — including driver demographics, vehicle characteristics, road conditions, environmental factors, and accident causes — to support policymakers, traffic authorities, and transportation planners in developing effective prevention strategies.

---

## 📋 Objectives

**Primary Objective:**
Analyze road traffic accident data and identify the major factors affecting accident severity.

**Specific Objectives:**
- Analyze the distribution of accident severity levels
- Identify the most common causes of accidents using Pareto analysis
- Examine the impact of driver age and driving experience on accident severity
- Study accident patterns across weather and lighting conditions
- Investigate the relationship between road characteristics and accident outcomes
- Evaluate vehicle-related factors contributing to accidents
- Identify high-risk driver groups through risk segmentation
- Build a machine learning model to predict accident severity
- Provide actionable recommendations to improve road safety

---

## 📊 Dataset

**File:** `RTA.csv`

| Column | Description |
|--------|-------------|
| `Time` | Time of accident occurrence |
| `Day_of_week` | Day the accident occurred |
| `Age_band_of_driver` | Driver age group (Under 18 / 18–30 / 31–50 / Over 51) |
| `Sex_of_driver` | Gender of the driver |
| `Driving_experience` | Years of driving experience |
| `Type_of_vehicle` | Category of vehicle involved |
| `Owner_of_vehicle` | Ownership type of the vehicle |
| `Area_accident_occured` | Urban or rural area |
| `Lanes_or_Medians` | Road lane configuration |
| `Road_allignment` | Road alignment type |
| `Types_of_Junction` | Junction type at accident location |
| `Road_surface_type` | Type of road surface |
| `Road_surface_conditions` | Condition of road surface |
| `Light_conditions` | Lighting at time of accident |
| `Weather_conditions` | Weather at time of accident |
| `Type_of_collision` | Nature of the collision |
| `Number_of_vehicles_involved` | Total vehicles involved |
| `Number_of_casualties` | Total casualties resulting |
| `Vehicle_movement` | Movement of vehicle at time of accident |
| `Cause_of_accident` | Primary cause of the accident |
| `Accident_severity` | Target variable — Slight / Serious / Fatal |

> **Dataset Size:** 12,316 records × 32 original features (21 retained after preprocessing)

---

## 📁 Project Structure

```
accident-severity-prediction/
│
├── Accident Severity Prediction & Risk Analytics.ipynb            # Jupyter Notebook — EDA & ML
├── Accident Severity Prediction & Risk Analytics Dashboard.pbix   # Power BI Dashboard
├── RTA.csv                                                        # Dataset
├── images                                                         # Images
├── License                                                        # LICENSE
└── README.md                                                      # Project documentation
```

---

## 🔍 Analysis Phases

### Phase 1 — Data Collection & Understanding
- Imported core libraries: `numpy`, `pandas`, `matplotlib`, `seaborn`, `plotly`
- Loaded `RTA.csv` and inspected shape, column names, data types, and statistical summary

### Phase 2 — Data Cleaning & Preprocessing
- Identified and dropped 10 high-missing or low-value columns (`Service_year_of_vehicle`, `Defect_of_vehicle`, `Casualty_severity`, etc.)
- Replaced remaining missing values in 11 categorical columns with `'Null'` to preserve all records
- Confirmed **zero duplicate rows** across all 12,316 records

### Phase 3 — Univariate Analysis
- Pareto chart of accident causes (80/20 principle)
- Driver age distribution histogram with KDE
- Vehicle type treemap
- Weather conditions bar chart
- Accident severity distribution bar chart

### Phase 4 — Bivariate Analysis
- Driver age vs. accident severity heatmap
- Driving experience vs. accident severity stacked bar chart
- Vehicle type vs. accident severity heatmap
- Light conditions vs. accident severity normalized stacked bar chart
- Cause of accident vs. accident severity horizontal stacked bar chart

### Phase 5 — Multivariate Analysis
- Sunburst chart: Weather → Light Condition → Accident Severity
- Parallel categories diagram: Age → Experience → Light → Severity
- Bubble chart: Weather conditions vs. light conditions accident hotspots

### Phase 6 — Correlation Analysis
- Correlation heatmap: Number of vehicles involved vs. number of casualties
- Pair plot exploring the relationship between numerical variables

### Phase 7 — Risk Segmentation
- Radar chart: Accident risk profile by driver age group
- Identification of high-risk demographic segments

### Phase 8 — Accident Flow & Relationship Analysis
- **Sankey Diagram:** Flow from accident causes to severity levels
- **Chord Diagram:** Cause ↔ severity relationship strength
- **Network Graph:** Accident cause–severity relationship network

### Phase 9 — Machine Learning Model
- Random Forest Classifier for multi-class severity prediction
- One-hot encoding for categorical features
- 80/20 train-test split with accuracy evaluation

### Phase 10 — Business Insights
Key findings derived from the full analysis (see below).

### Phase 11 — Strategic Recommendations
Ten evidence-based recommendations for transportation authorities and policymakers.

### Phase 12 — Executive Summary, Future Scope & Conclusion
- Consolidated project summary and key takeaways
- Ten future research and development directions
- Final conclusions on road safety analytics

---

## 💡 Key Insights

1. **Young Drivers (18–30) Are the Highest-Risk Group** — This age band contributes the largest share of accident cases across all severity levels.
2. **Driver Inexperience Amplifies Risk** — Limited driving experience correlates strongly with higher accident frequency and severity.
3. **Human Behavior Dominates Accident Causes** — Speeding, rule violations, and distraction are primary causes, not vehicle or weather failures.
4. **Pareto Principle Holds** — A small number of accident causes account for approximately 80% of all incidents.
5. **Certain Vehicle Types Are Overrepresented** — A few categories contribute disproportionately to accident counts, warranting targeted safety measures.
6. **Normal Weather Conditions Dominate** — Most accidents occur in clear conditions, reinforcing that driver behavior is the primary risk factor.
7. **Poor Visibility Increases Severity** — Accidents under unfavorable lighting conditions show a higher proportion of serious and fatal outcomes.
8. **Multi-Vehicle Accidents Produce More Casualties** — Correlation analysis confirms that more vehicles involved leads to higher casualty counts.
9. **Accident Severity Is Unevenly Distributed** — Fatal and serious cases are concentrated around specific, identifiable risk factors.
10. **Environmental and Human Factors Interact** — The combination of weather, lighting, age, and experience jointly shapes accident outcomes.

---

## 📌 Strategic Recommendations

1. **Young Driver Safety Programs** — Targeted campaigns, defensive driving workshops, and mandatory training for drivers aged 18–30
2. **Strengthen Traffic Violation Enforcement** — Speed limits, seat belt compliance, and distracted driving regulations
3. **Improve Road Lighting Infrastructure** — Additional streetlights and reflective markings in high-risk locations
4. **Enhance Driver Licensing Requirements** — Graduated licensing systems and periodic driver reassessments
5. **Deploy AI-Based Traffic Monitoring** — Real-time surveillance for proactive accident risk detection
6. **Prioritize High-Impact Accident Causes** — Focus resources on the top causes identified by Pareto and Sankey analyses
7. **Improve Emergency Response Systems** — Smart dispatch technology to reduce post-accident response times
8. **Vehicle-Specific Safety Initiatives** — Targeted inspections and awareness for high-involvement vehicle categories
9. **Weather-Aware Traffic Management** — Real-time alerts and adaptive controls during adverse weather
10. **Develop Predictive Accident Risk Models** — Machine learning to identify high-risk scenarios before accidents occur

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| Python 3.x | Core programming language |
| Pandas | Data manipulation and preprocessing |
| NumPy | Numerical computations |
| Matplotlib & Seaborn | Static visualizations (bar charts, heatmaps, histograms) |
| Plotly | Interactive charts (Sankey, Treemap, Sunburst, Parallel Categories) |
| HoloViews + Bokeh | Chord diagram |
| NetworkX | Network graph analysis |
| Scikit-learn | Machine learning (Random Forest, accuracy metrics) |
| Jupyter Notebook | Analysis and reporting environment |
| Power BI | Executive dashboard and business reporting |

---

## ▶️ How to Run

### Jupyter Notebook

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/accident-severity-prediction.git
   cd accident-severity-prediction
   ```

2. Install required libraries:
   ```bash
   pip install numpy pandas matplotlib seaborn plotly holoviews bokeh networkx scikit-learn
   ```

3. Launch Jupyter Notebook:
   ```bash
   jupyter notebook Accident_Severity_Prediction___Risk_Analytics.ipynb
   ```

4. Update the dataset path in **Phase 1 → Step 2** to point to your local file:
   ```python
   project = pd.read_csv("RTA.csv")
   ```

### Power BI Dashboard

1. Open **Power BI Desktop**
2. Load `Accident_Severity_Prediction___Risk_Analytics_Dashboard.pbix`
3. If prompted, update the data source path to your local `RTA.csv` location

---

## 📄 License

This project is for academic and educational purposes.

---

## 🙋 Author

**Uday S.**
*Data Science Project | Road Safety & Accident Analytics Domain*

