# **NUCLEAR ENERGY OPERATIONS & MAINTENANCE ANALYTICS - EXCEL PORTFOLIO PROJECT**
**Introduction**  
The global nuclear energy industry is experiencing a major revival driven by data and AI power demands, with major plant life extensions, small modular reactor (SMR) partnerships and financing pushes to triple capacity by 2050. The nuclear energy industry has its own challenges which some are highlighted in this Excel portfolio project. There are 7 different projects in this portfolio. As an Analytical and results-driven Chemical/Process Engineer, I was interested in a Nuclear Industry Project to identify some of the common issues with current built, maintenance and operations. I set out to understand these common issues by analysing maintenance, reliability, supplier, inventory, compliance and financial data to identify cost drivers, operational risks and opportunities for improved asset performance.  

**Analysis Areas**  
To understand the Nuclear Energy Issues, I analysed these areas - Maintenance costs, Equipment reliability, Vendor performance, Regulatory compliance, Inventory optimisation and Downtime root causes by asking the following:
1.	Which vendor has most downtime?
2.	Which plant has the highest maintenance cost?
3.	Where is maintenance expenditure being generated, and what is driving cost?
4.	What is the top worst asset type most frequent among plants due to lost MWh and repeated issues?
5.	Which asset type required the most inspection visit?

**Excel Skill Used**  
The following Excel skills were utilized for analysis:  
•	Pivot Tables  
•	Pivot Charts  
•	DAX (Data Analysis Expressions)  
•	Power Query  
•	Power Pivot  
•	XLOOKUP  
•	VLOOKUP  

**Dataset**  
The dataset used for this project contains 5,000 simulated work-order and operational records representing a large asset-intensive energy organisation. The dataset is available in [Dataset 1](https://github.com/josephegbaiyelo5-lab/Excel-Portofolio-Project/blob/main/Nuclear%20Energy%20Project%20CSV/assets.csv),[Dataset 2](https://github.com/josephegbaiyelo5-lab/Excel-Portofolio-Project/blob/main/Nuclear%20Energy%20Project%20CSV/vendors.csv),[Dataset 3](https://github.com/josephegbaiyelo5-lab/Excel-Portofolio-Project/blob/main/Nuclear%20Energy%20Project%20CSV/workorders.csv) which provides a foundation for analysing data using Excel. It includes detailed information on  
•	Plants  
•	Problems  
•	Root Causes  
•	Budget  
•	Regulations  

**Skills**:  
**Power Query**  
Extract: I first used power query to extracts the original data (Assets.csv, Vendor.csv and Workorder.csv).  
Transform: Then I transformed each query by removing duplicates, trim spaces, clean spaces, standardised text, change data types, handle missing data and create new columns

Asset  
<img width="373" height="709" alt="image" src="https://github.com/user-attachments/assets/a6253d52-1af5-4bde-8ed9-31790826020c" />

Vendor  
<img width="391" height="795" alt="image" src="https://github.com/user-attachments/assets/48ba4782-bcf5-4156-a644-263b0fe9bb62" />

Workorders  
<img width="406" height="1363" alt="image" src="https://github.com/user-attachments/assets/367ca458-f9f4-4194-aa3b-f1b0c08c9889" />

Load: Finally, I loaded transformed queries into workbooks, setting the foundation for subsequent analysis. 

Asset   
<img width="995" height="541" alt="image" src="https://github.com/user-attachments/assets/6286215c-d27c-4dc3-8482-50dbb5f1db10" />

Vendor  
<img width="1030" height="480" alt="image" src="https://github.com/user-attachments/assets/9701f9d5-5c34-4200-ad36-691a19f63338" />

Workorders  
<img width="1036" height="483" alt="image" src="https://github.com/user-attachments/assets/827b8631-708d-4580-a9ec-69afca6d855c" />

**Power Pivot**  
Relationship: I used power pivot to establish relationship between Asset ID in Assets and  Asset ID in Workorders and also Vendor in Workorders to Vendor in Vendor.  

<img width="940" height="482" alt="image" src="https://github.com/user-attachments/assets/ff0664c6-338b-4148-9a4e-c7292b86f6e2" />


**Pivot Tables and DAX**  

Pivot Tables  
•	I created pivot tables for various areas to be analysed using filters, columns, rows and values to establish items that would to be used to create various KPIs, charts, tables and dashboards.  
•	Then I added new measure to calculate total cost, budget, cost variance, average downtime, critical jobs, open jobs, average risk, compliance rate, emergency cost, preventive cost, average delay, low stock and so on.  

DAX  
•	I used DAX to calculate total cost, budget, cost variance, average downtime, critical jobs, open jobs, average risk, compliance rate, emergency cost, preventive cost, average delay, low stock and so on. For example  
	Total Cost = SUM(WorkOrders[ActualGBP])  
	Budget = SUM(WorkOrders[BudgetGBP])  
	Cost Variance = [Total Cost]-[Budget]  
	Average Downtime = AVERAGE(WorkOrders[DowntimeHours])  
	Vendor Spend = SUM(WorkOrders[ContractValue])  
	Compliance Rate = DIVIDE(CALCULATE(COUNTROWS(WorkOrders),WorkOrders[Compliance]="Compliant"),COUNTROWS(WorkOrders))  

**Project 1 : Executive KPI Dashboard Analysis and Insight**

•	Business Questions  
	Which vendor has most downtime?  
	Which plant has the highest maintenance cost?  
	What department spend most?  

•	Background Tables  

<img width="1029" height="164" alt="image" src="https://github.com/user-attachments/assets/ee71355e-e613-4bfc-84d1-0f3235aeb2a5" />  

<img width="350" height="211" alt="image" src="https://github.com/user-attachments/assets/63712d60-d307-4dee-87d5-ca6acc15336d" />  

<img width="425" height="239" alt="image" src="https://github.com/user-attachments/assets/38fcae1f-8ecd-48ea-82c5-11c2a3b5526b" />  

•	KPI Implementation  

<img width="940" height="70" alt="image" src="https://github.com/user-attachments/assets/1cc89f13-8b2f-41f3-b640-d47dad36d7a3" />  

•	Dashboard Implementation  

<img width="949" height="508" alt="image" src="https://github.com/user-attachments/assets/e0064271-0750-4d0f-a6f8-5f62d433b901" />  

•	Analysis and Insight  
	Downtime Risk: Vendor_18 has the highest average downtime of 19 hours within the operations department of Olukiluto plant.  
	Cost Risk: Heysham 1 plant has the highest maintenance cost of £243,358,630.  
	Departmental Cost: Maintenance department has highest cost exceeding budget by 15%.  

•	Recommendation Action  
	Control maintenance expenditure: Investigate plants and departments with persistent positive budget variance.  

