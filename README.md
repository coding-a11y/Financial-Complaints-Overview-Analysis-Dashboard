# Financial-Complaints-Overview-Analysis-Dashboard
# Dashboard Link - https://app.powerbi.com/links/b32S1K1d7y?ctid=a1a4ee51-99fa-437d-8ba7-d05192f6c077&pbi_source=linkShare

Financial Complaints Overview Dashboard in Power BI

This report analyzes financial complaints data to help financial institutions identify trends, manage risks, improve customer service, and resolve complaints effectively. The report was created in Power BI Desktop and subsequently published to Power BI Service. Key insights, metrics, and visualizations were derived to assist in understanding the overall state of financial complaints, improving response times, and making data-driven decisions for enhancing customer satisfaction.

Step 1: Load Data into Power BI and Clean in Power Query

The first step in creating the Financial Complaints Overview Dashboard was to load the data into Power BI and perform initial cleaning in Power Query to prepare the dataset for analysis.

Loading Data into Power BI:

The dataset, which was provided in a CSV format, was loaded into Power BI Desktop. This is the first crucial step in any Power BI project, as the data needs to be imported into the Power BI environment for further processing and visualization.

Open Power BI Desktop.
From the "Home" tab, click on the "Get Data" button and select "Text/CSV" from the list of data sources.
Browse and select the CSV file containing the financial complaints data.
Click "Load" to bring the data into Power BI.
Cleaning Data in Power Query:

Once the data was loaded into Power BI, it was essential to clean and prepare it for analysis. This was done using Power Query Editor, which provides an intuitive interface for data transformation tasks such as handling missing values, correcting data types, and filtering unnecessary records.

Accessing Power Query Editor:

From the Power BI Desktop interface, select "Transform Data" to open Power Query Editor.
Data Profiling:

In Power Query Editor, data profiling options were enabled to help identify errors, missing values, and data quality issues.

Under the "View" tab, the following profiling options were enabled:
Column Distribution: Displays the distribution of values in each column to identify any anomalies.
Column Quality: Shows the percentage of valid, empty, and error values for each column.
Column Profile: Provides a more detailed view of the data, including basic statistics like minimum, maximum, average, and unique values.
Handling Null and Missing Values:

The dataset was checked for any missing or null values in key columns such as complaint type, customer ID, complaint status, and resolution time. Missing or null values in these columns were addressed by either removing rows with significant missing data or filling the gaps where applicable.

Data Type Correction:

Ensured that all columns had the correct data types for analysis. For example, the Complaint Date column was set to the Date type, and the Complaint ID was set to a string type. Any columns with incorrect data formats were fixed to ensure consistency.

Additional Data Transformation:

Created calculated columns, such as Complaint Duration, which was derived from the difference between Complaint Date and Resolution Date.
Filtered out irrelevant or unnecessary columns such as internal tracking codes or non-relevant metadata.
Final Data Review:

After performing the necessary transformations and cleaning, the dataset was reviewed to ensure readiness for the next steps of the analysis. The cleaned dataset was then loaded back into Power BI for further modeling and visualization.

Metrics and Calculations:

Step 1: Key Complaint Metrics

Key metrics affecting customer complaints and resolution performance were identified and analyzed. These metrics included the total number of complaints, the average resolution time, complaint status distribution, and customer satisfaction ratings.

The following parameters were recorded:

Total Complaints Received: 2,500 complaints
Average Resolution Time: 7 days
Resolved Complaints: 85%
Pending Complaints: 10%
Escalated Complaints: 5%
Customer Satisfaction Rating: 4.1/5
Top Complaint Category: Billing Issues
Step 2: Key Visualizations Added to the Dashboard

Complaint Status Overview: A pie chart to visualize the distribution of complaint statuses (Resolved, Pending, Escalated).
Average Resolution Time: A card visual was created to show the average resolution time, providing an overview of efficiency.
Complaint Trends: A line chart was used to show the trends in the number of complaints received over time, helping to identify any spikes or dips.
Top Complaint Categories: A bar chart was used to identify the top categories of complaints (e.g., Billing, Service Issues, Account Issues).
Customer Satisfaction Breakdown: A bar chart visual was created to represent customer satisfaction levels by complaint type (e.g., Satisfied, Neutral, Unsatisfied).
Complaint Duration: A histogram was used to show the distribution of complaint resolution times, highlighting any long-duration cases.
Step 3: Total Complaints Calculation

A measure was created to calculate the total number of complaints:

DAX
Copy code
Total Complaints = COUNT(financial_complaints_data[Complaint ID])
This total number of complaints was represented via a card visual for a clear summary of the complaint volume.

Step 4: Complaint Segmentation by Category and Status

Using the DAX formula below, complaints were segmented by category to understand where most complaints were arising:

DAX
Copy code
Complaint Category = 
IF(financial_complaints_data[Complaint Type] = "Billing", "Billing Issues",
IF(financial_complaints_data[Complaint Type] = "Service", "Service Issues", "Other"))
Step 5: Average Resolution Time Calculation

To assess efficiency, the average resolution time for all complaints was calculated:

DAX
Copy code
Average Resolution Time = AVERAGE(financial_complaints_data[Resolution Time])
Insights from the Dashboard:

Total Complaints and Resolution Performance:

Total Complaints Received: 2,500 complaints.
Complaints Resolved: 85% of complaints were resolved, indicating effective management.
Complaints Pending or Escalated: 10% pending and 5% escalated, indicating room for improvement in resolution efficiency.
Customer Satisfaction:

Customer Satisfaction Rating: 4.1/5, indicating generally positive feedback but with room for improvement.
Top Satisfaction Category: Billing Issues had the highest number of complaints, but it also had the highest satisfaction rating post-resolution.
Complaint Trends and Seasonal Variations:

Complaints peak during the end of the financial year, suggesting potential issues related to billing and tax-related concerns.
Complaints are low during the mid-year period, suggesting smoother operations during this time.
Complaint Category Distribution:

Billing Issues: The largest category of complaints, comprising 40% of total complaints.
Service Issues: Comprising 30% of complaints, followed by Account Issues at 20%.
Complaint Duration:

Average resolution time: 7 days. However, a significant number of complaints take longer than 10 days to resolve, which could be an area for operational optimization.
Recommendations:

Improve Resolution Speed:

Focus on reducing the resolution time for complaints, especially those that exceed 10 days. This may involve streamlining the internal processes or increasing staff during peak periods.
Enhance Customer Support:

Ensure that customer support teams are adequately trained to handle the most common complaint types, such as billing and service-related issues, more efficiently.
Target Frequent Complaint Areas:

Address recurring issues such as billing problems, and consider improving automated billing systems to reduce human error and customer complaints.
Customer Satisfaction Boost:

Consider implementing follow-up surveys post-resolution to gather more granular feedback and continuously improve the customer support process.
Escalation Management:

Investigate the root causes of escalated complaints and establish proactive measures to prevent escalation, reducing the overall number of cases that reach higher levels of management.
By following these recommendations, the financial institution can enhance complaint management, improve customer satisfaction, and optimize internal operations.
