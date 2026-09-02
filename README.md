# FinSight — Finance Analytics Dashboard (Power BI)

Real-time insights into transactions, customers, and risk — built end-to-end in Power BI, from raw data to interactive dashboard.

# Project Overview

FinSight is a two-page Power BI dashboard that gives a finance team real-time visibility into transaction health, customer behavior, and risk — in one place. It simulates a real-world analytics workflow: raw transactional data is profiled and cleaned in Power Query, modeled into a star-schema, enriched with DAX time-intelligence measures, and visualized through interactive, slicer-driven dashboards.

# Objectives:

Monitor transaction volume and value trends over time (monthly, yearly)
Break down performance by customer segment, gender, state, and occupation
Track transaction status (Success / Failed / Pending) to spot operational risk
Compare fees, tax, and transaction counts across every transaction type

# Data Sources

Two tables were loaded into Power BI and connected on Customer ID.

Finance Transactions (Fact table) Transaction ID , Transaction Date , Account ID , Customer ID , Transaction Type ,Channel , Merchant Category , Amount , Fee Amount , Tax Amount , Currency (INR) , Transaction Status , Is Fraud , Risk Score , Reference Number

Customer (Dimension table) Customer ID , First Name , Last Name , Gender , DOB , City , State , Occupation , Customer Segment , Annual Income , Join Date

# Data Cleaning (Power Query)

Before transforming, each column was reviewed using Column Distribution, Column Quality, and Column Profile in the View tab.

Issue	Fix
Transaction_Id contained duplicates	Identified and removed
Fee_Amount contained NULLs	Filled with the column average (₹14.52)
Channel had extra whitespace	Transform → Format → Trim
Amount contained negative values	Transform → Scientific → Absolute
Currency inconsistent casing	Transform → Format → UPPERCASE
Customer name split across two columns	Merged First Name + Last Name

# Data Modeling

The two tables were connected on Customer ID. A dedicated Calendar table was created to drive all date-based calculations and time intelligence

# Dashboards
1. Overview Analysis

5 KPI cards with YoY comparisons, a monthly trend area chart, transaction status donut, customer segment and state breakdowns, a transaction-type summary table, and a gender split — all controlled by Year, Dynamic Metric, Occupation, and Category slicers.
<img width="1357" height="717" alt="Screenshot 2026-09-01 214836" src="https://github.com/user-attachments/assets/b90b6f74-7fa6-4bdf-a8f3-a2aa7b3cd08f" />

2. Transactions

A detailed, filterable table of individual transactions — Transaction ID, date, customer name, transaction type, status, gender, customer segment, state, total amount, fees, and tax — alongside the same KPI cards and slicers for consistent context
<img width="1360" height="708" alt="Screenshot 2026-09-01 214854" src="https://github.com/user-attachments/assets/d620a5f5-3c92-4d55-b3d6-6ccbb07f3454" />

# Tools & Skills Used
Power Query — data profiling, cleaning, and transformation
Data Modeling — star-schema relationships, Calendar table
DAX — KPI measures, time intelligence, YoY calculations
What-If Parameters — dynamic, user-driven measure switching
Power BI Desktop — dashboard design, layout, and interactivity

# About This Project

This is a personal portfolio project built to demonstrate an end-to-end Power BI analytics workflow — from raw, messy data to a polished, decision-ready dashboard.
