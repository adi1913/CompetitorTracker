Agile Documentation: RealTimeTracker Notification System

Project Overview:

The RealTimeTracker system monitors competitor product prices and customer reviews, sending real-time notifications via email when significant changes or trends are detected.

Modules & Files
-------------------------------------------------------------------
1. Data Ingestion

Files:

flipkart_product_details.csv
previous_prices.csv
flipkart_reviews_unique.csv
previous_reviews.csv

Description:
Product and review data are ingested from CSV files. Previous data files are maintained for comparison.
-----------------------------------------------------------------------
2. Price Drop Notification

File:
price_notifier.py

Description:
Compares today’s and previous prices for each product. If a price drop ≥ 10% is detected, sends an email alert to stakeholders.
--------------------------------------------------------------------
3. Negative Review Notification

File:
price_notifier.py

Description:
Detects new negative reviews (ratings 1 or 2) by comparing today’s and previous review files. If 2 or more new negative reviews are found, sends an email alert.
--------------------------------------------------------------------

4. Data Update Automation
File:
price_notifier.py
Description:
After each run, today’s review file is copied to the previous review file to ensure accurate comparison in the next cycle.
--------------------------------------------------------------------

User Stories:

As a product manager, I want to receive email alerts when a competitor drops their product price by 10% or more, so I can react quickly.
As a customer support lead, I want to be notified when there are multiple new negative reviews, so I can address customer concerns proactively.
As a data analyst, I want the system to automatically update previous data files after each run, so comparisons are always accurate.
--------------------------------------------------------------------
Sprint Tasks:

Sprint 1: Data Setup
Prepare and validate product and review CSV files.
Ensure previous data files exist for comparison.

Sprint 2: Notification Logic
Implement price drop detection and email notification.
Implement negative review detection and email notification.

Sprint 3: Automation & Maintenance
Automate copying of today’s review file to previous review file after each run.
Add error handling for missing files and incorrect data formats.

Sprint 4: Testing & Deployment
Test notification system with sample data.
Deploy script for scheduled or manual execution.
-----------------------------------------------------------------
Acceptance Criteria:

Email is sent when a product price drops by 10% or more.
Email is sent when 2 or more new negative reviews are detected.
Previous review file is updated after each run.
Script handles missing files gracefully and logs errors.
---------------------------------------------------------------

Workflow Diagram
    
Start Script
    |
Check for Price Drops
    |
If detected, send email alert.
    |
Check for Negative Reviews
    |
If detected, send email alert.
    |
Update Previous Review File.
    |
End Script.
------------------------------------------------------------
Change Log:

v1.0: Initial implementation of price and review notification logic.
v1.1: Added automation for previous review file update.
v1.2: Improved error handling and logging.
-------------------------------------------------------------

References:

price_notifier.py (main notification logic)
CSV files in data directory (input data)
--------------------------------------------------------------

