# Task 2: Data Analysis

In task 2, I worked on analysing telemetry data collected by Daikibo and visualising it in Tableau to get an overview of the downtime across factories and device types. The step-by-step breakdown of the process is as follows:
* Set up Tableau
  - Installed Tableau and familiarised myself with its interface
* Data prep
  - Downloaded and extracted the daikibo-telemetry-data.json.zip file
  - Imported the unzipped JSON file into Tableau, making sure all data fields were correctly mapped for analysis
 
* Calculated measure field
  - Created a calculated measure field called `Unhealthy` with a fixed value of 10 to represent 10 minutes of downtime for every "unhealthy" status

 * Data visualisation
   - Bar chart 1 - created a bar chart representing downtime per factory, showing which factories experienced the most downtime
   - Bar chart 2 - created a 2nd bar chart to visualise downtime per device type for a more granular view of performance issues
  
* Dashboard creation
  - Built a dashboard combining both bar charts (screenshot below)
  - Set the downtime per factory chart as a filter, enabling interactive exploration of data. Seleting a factory displayed the correspondign downtime by device type.
  
<img width="1280" alt="tableau-dashboard" src="https://github.com/user-attachments/assets/237a1295-bb83-40e3-a58b-41e7708bb46d" />

This task gave me a deeper look what data visualisation and analysis using Tableau looks like, especially in creating an interactive dashboard.
