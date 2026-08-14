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

[Check_my_work_here](https://github.com/josephegbaiyelo5-lab/Excel-Portofolio-Project/blob/main/Nuclear%20Energy%20Project.xlsx)

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

**Project 2 : Maintenance Costs Analysis and Insight**  

•	Business Questions  
	Where is maintenance expenditure being generated, and what is driving cost?  

•	DAX Measures  
	Emergency Cost = CALCULATE(SUM(workorders[ActualGBP]), workorders[MaintenanceType]=”Emergency”)  
	Preventive Cost = =CALCULATE(SUM(workorders[ActualGBP]), workorders[MaintenanceType]="Preventive")  
	Emergency Cost % = DIVIDE([Emergency Cost],[Total Cost])  

•	Background Tables  

<img width="940" height="256" alt="image" src="https://github.com/user-attachments/assets/333e14fa-2ad9-4a27-805d-a05e3af0cce8" />  

•	KPI Implementation  

<img width="898" height="115" alt="image" src="https://github.com/user-attachments/assets/88821429-84e6-4010-811f-c732b56809f5" />  

•	Dashboard Implementation  

<img width="898" height="539" alt="image" src="https://github.com/user-attachments/assets/277266ec-033e-430a-94bf-e106bcd224de" />  

•	Analysis and Insight  
	Emergency maintenance accounts most in the safety department with 25.5%, suggesting an opportunity to increase preventive maintenance on high-failure assets.  
	Emergency maintenance accounts most in December, which is about 31.3%.  

•	Recommendation Action  
	Reduce emergency maintenance: Investigate high-failure assets and increase targeted preventive maintenance.  

**Project 3 : Equipment Reliability Dashboard Analysis and Insight**

•	Business Questions  
	Which plant is the most aged?  
	What is the failure rate of the oldest asset?  
	What is the top worst asset type most frequent among plants due to lost MWh and repeated issues?  
	Which asset type required the most inspection visit?  

•	Background Tables  

<img width="940" height="701" alt="image" src="https://github.com/user-attachments/assets/a723f9bb-458e-4bac-b2c3-38236f11b850" />  
	Skill: I used VLOOKUP to retrieve asset type from Assets workbook.  


<img width="544" height="938" alt="image" src="https://github.com/user-attachments/assets/6a645a80-e21d-49f0-86ab-64788fc1c9e2" />  

•	KPI Implementation  

<img width="940" height="92" alt="image" src="https://github.com/user-attachments/assets/8ddb4b2e-c5aa-4581-bd64-ad9a96041d98" />  

•	Dashboard Implementation  

<img width="940" height="576" alt="image" src="https://github.com/user-attachments/assets/283f3e18-1160-49c4-af03-7bc2c23e2273" />  

•	Analysis and Insight   
	Three out of the six plants – Bruce A, Diablo Canyon and Olkiluoto are the most aged plants with an average asset age of 23 years. This information would help management to plan when considering the next phase of new built.  
	Olkiluoto is the most aged plant with most average failure rate of 6.05.  
	Sensor is the least reliable asset type repeated by two of the six plants resulting from lost MWh and repeated issues.  
	Generator requires the most frequent inspection visit.  

•	Recommendation Action    
	Improve equipment reliability: Review asset type issues with suppliers to see if more reliable asset can be purchased. 

**Project 4 : Vendor Performance Scorecard Analysis and Insight**  

•	Business Questions  
	Which vendor has the most spend?  
	Which country has the most average vendor delay?  
	Who are the top 3 vendors requiring performance improvement?  
	Which vendor has the highest total spend?  
	Which vendor complied most with regulatory requirements?  
	Which vendor exceeded budget most?  

•	DAX Measures    
	Average Delay (Days) =AVERAGE(workorders[ProcurementDelay])  
	Vendor Spend =SUM(workorders[ContractValue])  
	Late Deliveries = =CALCULATE(COUNTROWS(workorders), workorders[ProcurementDelay]>0)  
	Late Deliveries % =DIVIDE([Late Deliveries],[Total Work Orders],0)  

•	Background Tables  

<img width="964" height="858" alt="image" src="https://github.com/user-attachments/assets/3d8d6602-dc27-4aba-939c-d8d6a6437ac1" />  
	Skill: I used XLOOKUP to retrieve countries from Vendor workbook.  

<img width="940" height="391" alt="image" src="https://github.com/user-attachments/assets/638bf78f-186d-4966-8143-d4ea9b386e23" />  
	Skill: I used a weighted % to determine the score where delivery performance 40%, compliance 30% and cost performance 30%. Then I used an IFS statement to determine the rating by grading what is excellent, good etc. - IFS(score>90%,"Excellent",score>75%,"Good",score>60%,"Needs Improvement",TRUE,"Poor").  

•	KPI Card Implementation  

<img width="940" height="97" alt="image" src="https://github.com/user-attachments/assets/1733199c-afa0-4850-884a-465d275b8e65" />  

•	Scorecard Implementation  

<img width="861" height="648" alt="image" src="https://github.com/user-attachments/assets/b6de19ec-5455-42a0-9424-d87ce89b76d8" />  

•	Analysis and Insight  
	Vendor_27 has most spent of £24,076,624 in the Heysham 1 plant.  
	Vendor in United State of America caused the most average delay of 55.1 days in supplying Torness plant.  
	The top 3 most vendors requiring performance improvement are Vendor_2, Vendor_28 and Vendor_7 with late deliveries of 99.25%, 98.14% and 98% respectively.  
	Vendor_13 has the highest total spend of £89,147,397.  
	Vendor_4 has the highest compliance rate of 56.76%.  
	Vendor_2 exceeded the budget most by 18.43%.  

•	Recommendation Action  
	Improve vendor performance: Review contracts with suppliers showing consistently high delivery delays.  

**Project 5 : Regulatory Compliance Dashboard Analysis and Insight**

•	Business Questions    
	Which reactor type cost management most fines?  
	How many fines did high risk areas generated?  
	Which plant has the lowest audit score?  
	What month in 2025 had the highest audit score?  

•	Background Tables  

<img width="940" height="307" alt="image" src="https://github.com/user-attachments/assets/5d3a1eb9-f43e-4fcf-8b7d-ae2c30bdb5e5" />  

<img width="309" height="456" alt="image" src="https://github.com/user-attachments/assets/a3c94d66-2468-4a03-8710-63ca2ea8abf3" />  

•	KPI Implementation  

<img width="940" height="94" alt="image" src="https://github.com/user-attachments/assets/f32ae302-38ab-4681-b8ca-aa17964c4bb2" />  

•	Dashboard Implementation    

<img width="940" height="439" alt="image" src="https://github.com/user-attachments/assets/b70d996e-3eae-48cd-a74c-cd9e1453b80e" />  

•	Analysis and Insight  
	Pressurised Water Reactor (PWR) costed most fines of £10,419.253.  
	High risk areas generated 1773 fines.  
	Torness plant scored lowest audit score of 33.06%.  
	February 2025 has the highest audit score of 4309.  

•	Recommendation Action  
	Improve regulatory compliance performance: Investigate reactor types and plants with consistently high fines.  

**Project 6 : Inventory Optimisation Dashboard Analysis and Insight**  

•	Business Questions  
	Do we have the right parts available when required?  
	Which plant is reorder most needed?  
	Which department has the least negative stock?  
	What is the general status of the current stock?  

•	DAX Measures  
	Average Inventory =AVERAGE(workorders[InventoryLevel])  
	Negative Stock = CALCULATE(DISTINCTCOUNT(workorders[InventoryPart]),workorerrs [InventoryLevel]<0)  
	Low Stock =CALCULATE(DISTINCTCOUNT(workorders[InventoryPart]),FILTER(workorders,workorders[InventoryLevel] >0 && workorders[InventoryLevel] <= workorders[ReorderPoint]))  
	Reorder Needed =CALCULATE(DISTINCTCOUNT(workorders[InventoryPart]),FILTER(workorders,workorders[InventoryLevel] <= workorders[ReorderPoint]))  

•	Background Tables  

<img width="940" height="434" alt="image" src="https://github.com/user-attachments/assets/2f011b0d-6498-4a09-bb7b-1441ffb495f2" />  

<img width="942" height="520" alt="image" src="https://github.com/user-attachments/assets/e2857cb1-0ea4-45d0-8150-0b82a25cf8d2" />  
	Skill: I used an IF statement to determine the inventory status whether it is negative stock, reorder point or healthy. For example: IF(current stock<0,"Negative Stock",IF(current stock<=Reorder,"Reorder Point","Healthy")) then I used conditional formatting to determine the colours  

<img width="777" height="359" alt="image" src="https://github.com/user-attachments/assets/d992f73e-ba56-4e3f-be05-b55a2c249012" />  

•	KPI Implementation  

<img width="940" height="81" alt="image" src="https://github.com/user-attachments/assets/80215c02-9698-4f0e-82de-8fabb9eda685" />  

•	Dashboard Implementation  

<img width="940" height="699" alt="image" src="https://github.com/user-attachments/assets/c36f137e-37f0-4369-bfbb-1135244fedaf" />  

•	Analysis and Insight  
	360 reorder part needed which includes 43 negative recorded stock balances.  
	Diablo Canyon plant requires the highest number of orders, which is 109.  
	Safety Department has the least negative stock of 1.  
	General status of current stock is 100% Healthy.  

•	Recommendation Action  
	Optimise inventory: Prioritise replenishment of critical parts below reorder levels.  

**Project 7 : Downtime Root Cause Dashboard Analysis and Insight**  

•	Business Questions  
	What causes most downtime?  
	Which plant loses most MWh?  
	Which problem results into most downtime?  
	Which reactor type is costing management the most?  

•	Background Tables  

<img width="940" height="998" alt="image" src="https://github.com/user-attachments/assets/e94b91f0-1ae3-4d10-b4b1-da885e7989c8" />  

•	Dashboard Implementation  

<img width="940" height="624" alt="image" src="https://github.com/user-attachments/assets/c36daf72-290f-4c51-8f77-58c47aada9c7" />  

•	Analysis and Insight  
	Design and unknown root causes result in most downtime.  
	Diablo Canyon plant with 350866.6 MWh results in most MWh lost.  
	Valve leak with design root cause causes most downtime of 1893 hours.  
	BWR within Olkiluoto plant is costing management the most with 81046.4 MWh lost but Heysham 1 plant has the highest combined MWh lost of 218,258.5 MWh from PHWR, PWR and SMR.  

•	Recommendation Action  
	Reduce downtime: Fix the top two root causes to eliminate 80% of the total downtime.  
