# Coffee Sales PowerBI Dashboard
Coffee Sales Dataset | PowerBI (Power Query and DAX)

<br>

## 📘 Project Overview
Built an interactive **Power BI** dashboard using **Power Query** and **DAX** to analyze coffee vending machine sales data, uncovering product performance, payment behavior, and peak sales periods to support data-driven decisions.  

<img width="1436" height="806" alt="image" src="https://github.com/user-attachments/assets/59c91b3b-2425-4436-8047-def6c46968a2" />


## 💼 Business Problem

The coffee vending machine business needs visibility into its sales performance to understand customer purchasing behavior, product popularity, payment preferences, and time-based sales patterns. Without a centralized view, it is difficult to identify top-performing products, peak sales periods, and overall revenue trends that can inform restocking and operational decisions.

This dashboard provides a concise, one-page overview of coffee sales performance to support data-driven decision-making.

<br> 

## ❓ Business Questions
1. How much total revenue is generated from coffee sales?
2. What is the total transactions over the selected period?
3. What is the average number of transactions per day?
4. What percentage of customers pay using card versus cash?
5. How do sales trend over time?
6. Which coffee products are the most popular by number of transactions?
7. Which coffee products contribute the most to total revenue?
8. At what hours of the day do most coffee sales occur?

<br>

## 🔍 Key Insights

* The business generated $115K+ in revenue from approximately 3,600 cups of coffee sold, indicating steady and reliable demand for vending machine coffee.
* Average daily sales are around 10 transactions per day, suggesting consistent baseline usage rather than volatile demand spikes.
* Monthly revenue remains relatively stable throughout the year, with moderate peaks during select months, indicating predictable consumption patterns rather than strong seasonality.
* Popular items such as Americano with Milk and Latt contribute the highest revenue, making them core offerings.
* Over 97% of transactions are made using card payments, showing a clear customer preference for cashless transactions.
* Coffee sales peak during morning to mid-day hours, aligning with workday routines and break times.

<br>

## 📈 Business Recommendations
* Focus inventory and availability on top-performing coffee products to maximize revenue efficiency.
* Maintain and optimize card payment systems, as cash transactions contribute minimal value.
* Align restocking and machine maintenance schedules with peak sales hours to minimize downtime.

<br>

## 🛠 Tools Used
- Power BI
- Power Query
- DAX
- Data Visualization

<br>

## 🔄 Approach
1. Loaded the coffee sales dataset into Power BI.
2. Cleaned and prepared the data using Power Query by:
  * Ensuring correct data types
  * Removing unnecessary columns
3. Created DAX measures to calculate key KPIs:
    * `Total Revenue`

         ```DAX
         Total Revenue = SUM(coffee_sales[money])
         ```
    * `Total Transactions`

         ```DAX
         Total Transactions = COUNTROWS(coffee_sales)
        ```
    * `Average Transactions per Day`

        ```DAX
        Avg Transactions per Day = DIVIDE([Total Transactions], DISTINCTCOUNT(coffee_sales[date]))
        ```
    * `% card payments`
      
      ```DAX
      Card Payments = CALCULATE (COUNTROWS (coffee_sales),coffee_sales[cash_type] = "card")   
      % Card Payments= DIVIDE ([Card Payments],[Total Transactions])
      ```
4. Added calculated columns using DAX to support time-based analysis
    * `year`
    
        ```DAX
            year = YEAR(coffee_sales[date])
        ```
    * `month`
      
        ```DAX
          month = FORMAT (coffee_sales[date], "MMM" )
        ```
    * `hour`
       
        ```DAX
          hour = HOUR(coffee_sales[datetime])
        ```
5. Designed an interactive one-page dashboard including:
    * KPI cards for high-level performance tracking
    * Sales trend analysis over time
    * Coffee product performance analysis
    * Payment method 
    * Hour-of-day sales distribution
6. Implemented Month and Year slicers for dynamic filtering.
7. Applied consistent formatting, color themes, and conditional highlighting to improve readability and visual clarity.

<br>

## 📊 Dataset
Source: [Coffee Sales](https://www.kaggle.com/datasets/ihelon/coffee-sales)    
Key columns include:`date`,`cash_type`,`money`,`coffee_name`

<br>
<br>
<br>
If you found this project helpful or insightful, a ⭐ on this repo would make my day !! 😊
