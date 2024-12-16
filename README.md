# 2-Data Visualization

## This assignment is about data transfoprmation and Visualization of a 'Global Superstore' using Power Query and Power BI

### Steps has been completed in the process.

#### 3 Sheets has been found in the workbook named as Orders, People and Return.

Loaded the 'Global Superstore' file into Power Query to transform and load into Power BI for further process

Promoted the Headers

Removed the 'Null' values

Removed duplicates and blank rows

Seperate the column using delimiter(Product Name)

Removed the unwanted column(Product Name has been seperated by delimiter and removed the newly created column)

Reordered the column('Returned')

Created the relationship between Given Table(Orders to People as Many to One with Single  
Filter and Returns to Orders as One To One with Both Filter)

Created new Table in correspondance with Orders table as "Profit Margin"

'Profit Margin = ADDCOLUMNS(Orders,"Profit Margin",IF(Orders[Sales]<>0,(Orders[Profit]/Orders[Sales]) * 100, 0),"Profit Category",IF(IF(Orders[Sales]<>0,(Orders[Profit]/Orders[Sales])*100,0)>=50,"Higher Profit","Lower Profit"))'


YourCopyableTextblock       Profit Margin = ADDCOLUMNS(Orders,"Profit Margin",IF(Orders[Sales]<>0,(Orders[Profit]/Orders[Sales]) * 100, 0),"Profit Category",IF(IF(Orders[Sales]<>0,(Orders[Profit]/Orders[Sales])*100,0)>=50,"Higher Profit","Lower Profit"))
