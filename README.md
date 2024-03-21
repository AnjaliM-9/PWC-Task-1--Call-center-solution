# PWC-Task-1-Call-center-solution
## Problem Statement:
Possible KPI’S required :
- Overall customer satisfaction
- Overall calls answered/abandoned
- Calls by time
- Average speed of answer
- Agent’s performance quadrant -> average handle time (talk duration) vs calls answered
## Datasource and Preparation
Data set for this task was provided by PWC, Call center Dataset. [01 Call-Center-Dataset.xlsx](https://github.com/AnjaliM-9/PWC-Task-1--Call-center-solution/files/14696709/01.Call-Center-Dataset.xlsx)
-The dataset contained  5002 rows and 10 columns.
- Applied Format as table in excel sheet
Steps performed for Data transformation in Power Query after the dataset loaded into Microsoft Power BI Desktop for modelling:
- Each of the columns in the table were validated to have the correct data type
- Inserted a calculated column into query table to evaluate for month wise slicer.
- Inserted two calculated columns into query table to calculate  minutes and seconds of call duration field.
- Filtered out rows having missing values across multiple fields.
## Data Modeling
It is a flat file schema
![Picture 3](https://github.com/AnjaliM-9/PWC-Task-1--Call-center-solution/assets/155083462/831dc5cc-6692-4fae-a618-291a5b1599e8)
## Data Analysis (DAX)
Following are the measures created: -
-  ```Overall customer satisfaction  = AVERAGEX(Call_center,Call_center[Satisfaction rating])```
- ```abandoned %  = DIVIDE([Not Answered calls],COUNT(Call_center[Call Id]),0)```
- ```Average speed of answer = AVERAGEX(Call_center,Call_center[Speed of answer in seconds])```
- ```Answered calls = COUNTROWS(FILTER(Call_center,Call_center[Answered (Y/N)]="Y"))```
- ``` Non blank ratings count = COUNTA(Call_center[Satisfaction rating])```
- ``` Not Answered calls = COUNTROWS(FILTER(Call_center,Call_center[Answered (Y/N)]="N"))```
- ``` Resolution% = DIVIDE([Resolved calls],COUNT(Call_center[Answered (Y/N)]),0)*100```
- ``` Resolved calls = COUNTROWS(FILTER(Call_center,Call_center[Resolved]="Y"))```
- ``` Unresolved calls = COUNTROWS(FILTER(Call_center,Call_center[Resolved]="N"))```
- ```Avrg handle in sec = (Call_center[Minute]*60)+Call_center[Second]```
## Dashboard (Data Visualization)
### Call centre solution dashboard

![PWC-Call center solution](https://github.com/AnjaliM-9/PWC-Task-1--Call-center-solution/assets/155083462/9f78a643-012c-4ac3-a1d6-37222159e4b3)
## Insights!








