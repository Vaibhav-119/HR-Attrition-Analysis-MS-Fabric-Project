# HR Attrition Analysis — Microsoft Fabric & Power BI

An end-to-end HR analytics project built using **Microsoft Fabric and Power BI** to understand employee attrition and identify the factors that may be associated with employees leaving an organization.

The goal was not just to build a dashboard, but to take the data through a complete analytics workflow, from data preparation and storage to modeling, visualization, security, and deployment.

---

## Project Overview

Employee attrition can have a direct impact on hiring costs, productivity, and workforce planning.

In this project, I analyzed employee data to answer questions such as:

* How high is the overall attrition rate?
* Which departments have higher attrition?
* Which job roles are losing the most employees?
* Does salary have a relationship with attrition?
* Which age groups have higher attrition?
* Is attrition different between male and female employees?
* Does business travel affect attrition?
* Is working overtime associated with higher attrition?
* How do marital status and education field relate to employee attrition?

The final result is a two page Power BI report with an **Overview** page for the main findings and a **Deep Dive** page for more detailed analysis.

---

## Final Report

**HR Attrition Analysis — Fabric App**

[Open the Microsoft Fabric App](https://app.fabric.microsoft.com/groups/4136460f-5735-4d3d-a59e-f799cead1f81/reports/54f004f6-8ecd-456d-8963-3d4f04191ccd/9b937ffea0c13a827341?redirectedFromSignup=1&experience=power-bi)

---

## Tools & Technologies

* **Microsoft Fabric**
* **Dataflow Gen2**
* **Power Query**
* **Fabric Lakehouse**
* **Delta Tables**
* **Semantic Model**
* **Power BI Desktop**
* **DAX**
* **Power BI**
* **Column-Level Security (CLS)**
* **Fabric App**

---

## workflow

The project followed this workflow:

```text
CSV Dataset
     ↓
Dataflow Gen2
     ↓
Power Query Transformations
     ↓
Calculated Columns
     ↓
Fabric Lakehouse
     ↓
Delta Table
     ↓
Semantic Model
     ↓
Power BI Report
     ↓
Publish to Fabric
     ↓
Column-Level Security
     ↓
Fabric App
```

### 1. Data Preparation

I imported the CSV dataset into **Dataflow Gen2** and used Power Query to perform the required transformations.

This included cleaning the data and creating calculated columns needed for the analysis.

### 2. Data Storage

After the transformations, the processed data was loaded into a **Fabric Lakehouse** as a Delta table.

The main employee table used in the project was:

`hr_employees`

### 3. Semantic Model

I created a semantic model on top of the Lakehouse table.

Since the dataset was relatively small and the analysis was centered around a single employee-level table, I kept the model simple rather than introducing unnecessary tables and relationships.

For a larger production dataset, a star-schema approach could be more appropriate.

### 4. Power BI Report

I created the report in Power BI Desktop and built the required measures and visuals using DAX.

The report contains two pages:

* **Overview**
* **Deep Dive**

---

# Dashboard

## Overview

The Overview page gives a quick picture of the organization's attrition situation.

It includes KPI cards for:

* Attrition Rate
* Employees Left
* Total Headcount
* Average Monthly Income
* Average Tenure of Leavers

It also contains analysis of attrition by:

* Department
* Job Role
* Salary Band

There are slicers for:

* Department
* Gender
* Salary Band

### Overview Screenshot

![Overview Page](<img width="1551" height="911" alt="Screenshot 2026-09-24 233317" src="https://github.com/user-attachments/assets/8d50d7e9-f77d-4b84-bee9-c6dd745e093c" />
)

---

## Deep Dive

The Deep Dive page focuses on the employee characteristics that may be associated with attrition.

The analysis includes:

* Age Group
* Gender
* Education Field
* Marital Status
* Business Travel
* Overtime

This page makes it easier to move from the overall attrition number to specific employee segments.

### Deep Dive Screenshot

![Deep Dive Page](<img width="1437" height="879" alt="Screenshot 2026-09-24 222542" src="https://github.com/user-attachments/assets/c7df85d0-23d4-40ed-9e58-6bfc91d794ae" />
)

---

# Key Findings

Some of the notable findings from the dashboard were:

* Overall attrition was **16.1%**.
* **Sales** had the highest attrition rate among the departments shown.
* **Sales Representatives** had a particularly high attrition rate compared with other job roles.
* Employees in the **Under 3k salary band** had the highest attrition rate.
* The **18–25 age group** had the highest attrition rate among the age groups analyzed.
* Employees who worked **overtime** had considerably higher attrition than those who did not.
* Employees who travelled **frequently for business** showed higher attrition than non-travellers.
* **Single employees** had higher attrition than married or divorced employees.

These numbers don't by themselves prove that one factor causes employees to leave. They show patterns in the dataset that could be investigated further by an HR team.

---

# Data Security

One part of the project I specifically wanted to include was **data security**.

Monthly income is sensitive employee information, so after publishing the report to Microsoft Fabric, I applied **Column-Level Security (CLS)** to the `MonthlyIncome` column.

### CLS Screenshot

![Column Level Security](<img width="1528" height="864" alt="Screenshot 2026-09-24 225752" src="https://github.com/user-attachments/assets/32d30db9-8e58-463a-a83e-7b986a31c783" />
)


---

# What I Learned

This project helped me understand that a BI project is more than just creating charts.

I got hands-on experience with the complete flow:

**Prepare → Store → Model → Analyze → Secure → Publish**

Some of the main things I worked with were:

* Data preparation using Dataflow Gen2 and Power Query
* Working with a Fabric Lakehouse
* Delta tables
* Semantic models
* DAX measures
* Power BI report design
* Interactive slicers and visual analysis
* Column-Level Security
* Publishing analytics solutions in Microsoft Fabric
* Creating a Fabric App

---

# Project Structure

```text
HR-Attrition-Analysis/
│
├── images/
│   ├── hr_attrition_overview.png
│   ├── hr_attrition_deepdive.png
│   ├── fabric_cls_monthly_income.png
│   └── fabric_lakehouse.png
│
├── HR Attrition Analysis.pbix
│
└── README.md
```
