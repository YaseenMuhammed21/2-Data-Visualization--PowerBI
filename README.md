# 2-Data Visualization

## This assignment is about data transformation and visualization of a 'Global Superstore' using Power Query and Power BI

### Steps has been completed in the process.

#### 3 Sheets has been found in the workbook named as Orders, People and Return.

1. Loaded the 'Global Superstore' file into Power Query to transform and load into Power  BI for further process

2. Promoted the Headers

3. Removed the 'Null' values

4. Removed duplicates and blank rows

5. Seperate the column using delimiter(Product Name)

6. Removed the unwanted column(Product Name has been seperated by delimiter and removed the newly created column)

7. Reordered the column('Returned')

8. Created the relationship between Given Table(Orders to People as Many to One with Single  
Filter and Returns to Orders as One To One with Both Filter)

### DAX Operations

1. Created new table in correspondance with Orders table as "Profit Margin" with the column named as 'Profit Margin' and 'Profit Category'
##
    Profit Margin = ADDCOLUMNS(SELECTCOLUMNS(Orders,"Order",Orders[Order ID],"Sale",Orders[Sales],"Profit",Orders[Profit]),"Profit Margin",IF([Sale]<>0,([Profit]/[Sale])*100,0),"Profit Category",IF(IF([Sale]<>0,([Profit]/[Sale])*100,0)>=50,"Higher Profit","Lower Profit"))

3. Created new table to find the 'Profit' and 'Shipment cost' ratio as "Profit to Shipping Cost Ratio" with column named as 'Profit to Shipping Cost Ratio'
##
    Profit to Shipping Cost Ratio = ADDCOLUMNS(Orders,"Profit to Shipping Cost Ratio",IF(Orders[Shipping Cost]<>0,Orders[Profit]/Orders[Shipping Cost],0))

3. Created new table named as "Sales and Profit in Returned Items" to find the profit from the returned item where which the 'Orders' table and the 'Return' related One to One and 'Bi-Direction'
##
    Sales and Profit in Returned Items = SELECTCOLUMNS(Returns,"Order ID",Returns[Order ID],"Returned",Returns[Returned],"Sales",RELATED(Orders[Sales]),"Profit",RELATED(Orders[Profit]))

4. Added a column in Orders table as 'Rounded Profit'
##
    Rounded Profit = ROUND(DIVIDE(Orders[Profit], Orders[Sales]) * 100, 2)

5. Created the new measures for 'Total Sale'
##
    Total Sale = SUM(Orders[Sales])
6. Created new table 'Sales Over Location'
##
    Sales Over Location = SELECTCOLUMNS(Orders,"order ID",Orders[Order ID],"Category",Orders[Category],"sales",Orders[Sales],"City",Orders[City],"Country",Orders[Country],"Region",Orders[Region],"Profit",Orders[Profit])

7. Created the column to find the difference between the 'Order Date' and the 'Ship Date'
##
    Shipment Duration = DATEDIFF(Orders[Order Date],Orders[Ship Date],DAY)

8. Created the measures 'Profit Percentage'
##
    Profit Percentage = DIVIDE(SUM('Profit Margin'[Profit]),SUM('Profit Margin'[Sale]))*100

### Visualization

1. Created the visual for Performance By Person to get the visualization of individual Sale Person
2. Created the visual to study Market across the world
3. Created the visual to study the Shipment scenario across the sale
4. Created the visual for market drill down to know the area to increase the sale
5. Created the Summary for the project

## We have used Stacked Bar Chart, Clustered Column Chart, Card, Slicer, Map, Line and Clustered Column Chart, Tree Map, Matrix, Scatter Chart and Gauge Chart

### Please find the video for visualization
##
    https://drive.google.com/file/d/1sX0O_B_B5lljyR2BdZvjDTO3xGbEZ-XJ/view?usp=drive_link
