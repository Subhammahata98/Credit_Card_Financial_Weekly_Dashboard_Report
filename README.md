# Credit_Card_Financial_Weekly_Dashboard_Report
Power BI Dashboard
Project Objective:
 To develop a comprehensive credit  card weekly dashboard that provides real-time insights into key performance metrics and trends, enabling stakeholders to monitor and analyze credit card operations effectively.
 Prepare CSV File and upload in Power BI
 Add Few column and measures by using DAX
 DAXQueries:
 AgeGroup = SWITCH(
 TRUE(),
 'customer'[Customer_Age] < 30, "20-30",
 'customer'[Customer_Age] >= 30 && 'customer'[Customer_Age] < 40, "30-40",
 'customer'[Customer_Age] >= 40 && 'customer'[Customer_Age] < 50, "40-50",
 'customer'[Customer_Age] >= 50 && 'customer'[Customer_Age] < 60, "50-60",
 'customer'[Customer_Age] >= 60, "60+",
 "unknown"
 )
 IncomeGroup = SWITCH(
 TRUE(),
 'customer'[Income] < 35000, "Low",
 'customer'[Income] >= 35000 && 'customer'[Income] <70000, "Med",
 'customer'[Income] >= 70000, "High",
 "unknown"
 )
  week2 = WEEKNUM(credit_card[Week_Start_Date].[Date])
 Revenue = 'credit_card'[Annual_Fees] + 'credit_card'[Total_Trans_Amt] + 'credit_card'[Interest_Earned]
 Current_week_Reveneue =
 CALCULATE(
 SUM('credit_card'[Revenue]),
 FILTER(
 ALL(credit_card),
 credit_card[week2] = 
MAX(credit_card[week2])))
 Previous_week_Reveneue =
 CALCULATE(
 SUM('credit_card'[Revenue]),
 FILTER(
 ALL(credit_card),
 credit_card[week2] = 
MAX(credit_card[week2])-1))
Project Insights- Week 53 (31st Dec)
 WoW change:
 • Revenue increasedby 28.8%,
 • Total Transaction Amt & Count increased by 2.22% & 61.11%
 • Customer count increased by 1.80%
 Overview YTD:
 • Overall revenueis 57M
 • Total interest is 8M
 • Total transaction amount is 46M
 • Male customers are contributing more in revenue 31M, female 26M
 • Blue & Silver credit card are contributing to 93% of overall transactions
 • TX,NY & CA is contributing to 68%
 • OverallActivation rate is 57.5%
 • OverallDelinquentrate is 6.06%
