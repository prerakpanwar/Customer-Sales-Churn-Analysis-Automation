# Customer-Sales-Churn-Analysis-Automation
Alteryx Automation (Saving Time 1 Hour to ~ 1.2 Seconds)

![Screenshot 2025-06-29 225534](https://github.com/user-attachments/assets/bff1e4e3-3f1e-45f0-87e4-1e9d2c244305)

### Customer Churn Analysis Automation using Alteryx

## Problem Statement

*Customer retention is a critical metric for businesses—especially those in retail, logistics, or subscription-based models. Identifying customers at risk of churn (i.e., those likely to stop purchasing or engaging) enables organizations to take proactive actions to improve loyalty, boost revenue, and reduce acquisition costs.*

However, without automation and real-time insight, tracking customer behavior and flagging churn risk is manual, delayed, and error-prone.

## Objective
Build an automated churn prediction workflow using Alteryx Designer, which:

Joins customer and transaction data

Detects the last transaction date per customer

Calculates days since last purchase

Flags customers who haven't transacted in the last 90+ days as "likely churned"

Outputs clean, actionable customer lists for marketing or retention teams

## Tools Used
Alteryx Designer

Formula Tool

Join Tool

Summarize Tool

Filter Tool

DateTimeDiff & DateTimeToday()

Excel Output

## Dataset Details
Customers.csv(Customer ID, Store Number, Segment, Address, State, ZIP, etc.)

Transactions.xml(Transaction ID, Customer ID, Product Name (mocked using logic), Order ID, Date, Sales Amount)

## Workflow Steps
*1. Data Preparation*
Loaded customer and transaction files

Selected only the necessary columns

Generated realistic product names using randomized logic (to simulate real scenarios)

*2. Joining Data*
Joined the datasets using Customer_ID

Validated unmatched records using Join outputs (L/R)

*3. Last Transaction Date*
Used a Summarize Tool to get the max(Date) for each customer

Renamed as Last Purchase Date

*4. Days Since Last Purchase*
Calculated time difference between today and last purchase date using:

DateTimeDiff(DateTimeToday(), [Last Purchase Date], "days")

*5. Churn Flagging*
Created a binary label:

IF [Days Since Last Purchase] > 90 THEN "likely churned"
ELSE "active"

*6. Filtering Results*
Used a Filter Tool to separate: Active customers & Likely churned customers

*7. Output*
Exported 2 Excel sheets: Customer Churned Likelihood.xlsx & Active Customers.xlsx

## Results
Out of 2,678 customers, 621 were flagged as likely churned

Churn flagging logic is dynamic — recalculates based on current date

Outputs are ready for use in: Retargeting campaigns, Sales prioritization, CRM alerts, Customer retention dashboards

## Business Use Cases
This churn analysis use case is applicable in many industries:

Industry Use Case
Retail & CPG Identify inactive buyers for coupon re-engagement
Logistics	Spot inactive accounts needing follow-up
SaaS/Subscriptions Detect inactive users before renewal
Healthcare Track patients who stopped visiting/checking in
Call Centers Prioritize at-risk customers for outreach

## Impact
Enables data-driven churn detection

Reduces manual effort and error in tracking inactivity

Supports proactive engagement strategies

Provides a repeatable, scalable solution using Alteryx
