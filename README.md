# 2-Data Visualization

## This assignment is about data transfoprmation and Visualization of a 'Global Superstore' using Power Query and Power BI

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

9. Created new Table in correspondance with Orders table as "Profit Margin" with the column named as 'Profit Margin' and 'Profit Category'
##
    Profit Margin = ADDCOLUMNS(Orders,"Profit Margin",IF(Orders[Sales]<>0,(Orders[Profit]/Orders[Sales]) * 100, 0),"Profit Category",IF(IF(Orders[Sales]<>0,(Orders[Profit]/Orders[Sales])*100,0)>=50,"Higher Profit","Lower Profit"))
