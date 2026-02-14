Vehicle-Fuel-Efficiency-and-Emissions-Analytics
This project is an end-to-end data analytics platform developed as part of a graduate course at the University of Maryland, Baltimore County (UMBC). It integrates environmental and automotive datasets to explore trends in CO₂ emissions, vehicle fuel economy, and electric vehicle adoption between 2015 and 2025.

Overview
Due to rising environmental concerns and regulatory pressures, this project aims to help stakeholders—including automakers, government agencies, consumers, and environmental groups—make data-driven decisions for sustainable transportation.

Key features include:

Data warehouse design using SQL Server
ETL pipelines built with SSIS (SQL Server Integration Services)
Interactive Power BI dashboards
Insights into emissions trends, fuel efficiency, and EV market share
Technologies Used
SQL Server Management Studio (SSMS) – Data storage and querying
SSIS (SQL Server Integration Services) – ETL pipeline creation
Power BI – Data visualization and dashboarding
Python – Initial data cleaning and merging
Data Sources: EPA, NOAA, Global Carbon Atlas, Bureau of Transportation Statistics
Project Structure
vehicle-efficiency-analytics/
│
├── datasets/                      # Sample or dummy versions of EPA/NOAA data
├── etl_scripts/                  # ETL package descriptions and SSIS screenshots
├── sql_queries/                  # SQL scripts for table creation and KPI calculations
├── powerbi_dashboards/          # PBIX files or dashboard snapshots
├── README.md                     # Project overview and instructions
├── LICENSE                       # MIT License (or applicable)
ETL Workflow (SSIS)
Extract: Load raw CSVs using flat file sources.

Transform:

Clean missing and null values
Normalize fuel type strings and date formats
Calculate new KPIs (e.g., CO₂ per vehicle, fuel cost efficiency)
Load: Push to normalized SQL Server tables

Dashboard Insights (Power BI)
CO₂ vs. Average Temperature (2015–2025)
Electric vs. Fuel Vehicle Sales Trends
Fuel Efficiency Leaders by Make and Model
Top Low CO₂ Emission Vehicles
Fuel Type Distribution Across Years
City-wise CO₂ Emission Trends
Key Outcomes
Identified leading low-emission and high-efficiency vehicle models
Tracked rise in EV market share and regional CO₂ patterns
Demonstrated positive correlation between emissions and temperature rise
Delivered visual tools to support sustainable transportation planning
