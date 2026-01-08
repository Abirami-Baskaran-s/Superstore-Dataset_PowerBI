Superstore Sales & Risk Analysis Dashboard

Project Overview

This Power BI dashboard provides a comprehensive analysis of the SampleSuperstore dataset, focusing on two primary objectives: Operational Performance and Risk Monitoring. By applying information hierarchy principles (F-Pattern and the 5-second rule), the dashboard allows stakeholders to immediately identify high-level KPIs before drilling down into regional performance and product-level risks.
Key Features

  *Executive Summary (KPIs): Instant visibility into Total Sales, Profit, and Margins.

  *Regional Performance: Bar chart analysis identifying the West and East regions as primary revenue drivers.

  *Category Distribution: Pie chart breakdown showing the balance between Technology, Furniture, and Office Supplies.

  *Risk Management Suite: Dedicated monitoring for "Loss Making Orders" and "High Discount Risk" to protect profit margins.

  *Interactive Slicers: Dynamic filtering by Customer Segment (Consumer, Corporate, Home Office) and Risk Status.

DAX Measures & Logic

The intelligence of this dashboard is powered by custom Data Analysis Expressions (DAX). Below are the key measures implemented:

1. Primary Business KPIs
   
 #Measure	DAX Formula	Description

 #Total Sales	SUM(Sales)	Aggregates gross revenue.
 
 #Total Profit	SUM(Profit)	Aggregates net earnings.
 
 #Profit Margin	DIVIDE([Total Profit], [Total Sales]) * 100	Percentage of revenue converted to profit.
 
 #Average Order Value	DIVIDE([Total Sales], [Order Count])	Average revenue generated per transaction.

3. Risk & Quality Metrics
   
 #Measure	DAX Formula / Logic	Purpose
 
 #Loss Making Orders	CALCULATE(COUNTROWS(), Profit < 0)	Counts transactions that resulted in a financial loss.
 
 #High Discount Risk	CALCULATE(COUNTROWS(), Discount > 0.6)	Tracks orders with dangerously high discounts (>60%).
 
 #Business Risk Level	SWITCH(TRUE()...)	A dynamic status indicator (Low, Medium, High, Critical) based on the volume of loss-making orders.
 
 #Data Quality Score	(Total - Risk) / Total * 100	Calculates a health percentage for the dataset.

Design Principles Applied

  *F-Pattern Layout: Placed the most critical KPIs in the top-left quadrant to align with natural reading patterns.

  *5-Second Rule: Designed the "Business Risk Level" and "Risk Status" gauge to communicate the health of the business in under five seconds.

  *Conditional Formatting: Implemented color-coded alerts (Red for loss, Green for profit) to provide immediate visual cues.

How to Use

  *Filter by Segment: Use the "Segment" slicer to see how Corporate vs. Consumer trends differ.

  *Cross-Filtering: Click on the "West" bar in the Regional chart to update the entire dashboard for that specific territory.

  *Risk Audit: Filter the "Business Risk Level" to "High" to identify specific sub-categories (like Tables or Supplies) that are dragging down profitability.

Technical Stack

  *Tool: Power BI Desktop

  *Language: DAX (Data Analysis Expressions)

  *Data Source: CSV (SampleSuperstore Dataset)
