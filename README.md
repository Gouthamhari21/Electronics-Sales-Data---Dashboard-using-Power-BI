To analyze sales performance across Category, Region, Time, and Payment Method between 2010 and 2025, and identify high-performing segments and improvement opportunities to increase revenue and profitability.

//Data Cleaning Process
1. Date Column Cleaning
1.	Data → From Table/Range → opens Power Query Editor
2.	Select Date column → Right-click → Duplicate Column
3.	Transform → Format → Trim
4.	Transform → Format → Clean
5.	Transform → Format → Capitalize Each Word
6.	Transform → Replace Values
o	Value To Find: st → Replace With: (leave empty) → OK
o	Repeat for nd, rd, th
7.	Right-click cleaned column → Change Type → Using Locale
o	Data Type: Date
o	Locale: English (United Kingdom) → OK
8.	Home → Close & Load (back to Excel)
9.	In Excel: Select column → Ctrl + 1 → Number → Custom → Type dd-mm-yy → OK
________________________________________
2. Text Columns Cleaning (Region, City, Customer Segment, Payment Method)
1.	Data → From Table/Range → Power Query Editor
2.	Select column → Transform → Trim (remove extra spaces)
3.	Transform → Format → Clean (remove non-printable characters)
4.	Transform → Format → Capitalize Each Word
5.	Transform → Replace Values → fix common typos if needed
6.	Home → Close & Load
________________________________________
3. Capitalize Text in All Columns with Text Data
1.	In Power Query Editor, select all text columns (Product Name, Category, Region, City, Salesperson, Customer Segment, Payment Method)
2.	Transform → Format → Capitalize Each Word
3.	Home → Close & Load
________________________________________
4. Correct Category Based on Product Name
1.	Create a reference table (Product Name → Correct Category):
Product Name	Correct Category
Tablet	Electronics
Drone	Electronics
Smartphone	Electronics
Monitor	Electronics
Camera	Electronics
Headphones	Accessories
Router	Electronics
Smartwatch	Wearable
Laptop	Electronics
Printer	Electronics
2.	In Power Query Editor:
o	Merge your main table with the reference table on Product Name
o	Keep the Correct Category column
o	Replace old Category column with Correct Category
3.	Home → Close & Load
THESE STEPS FOLLOWED FOR CITY AND REGION ALSO
________________________________________
5. Numeric Columns Cleaning (Units Sold, Unit Price, Discount, Total Sales, Profit)
1.	Data → From Table/Range → Power Query Editor
2.	Select numeric columns → Right-click → Change Type → Decimal Number / Whole Number
3.	Fix Units Sold if it contains text:
o	Transform → Detect Data Type
o	Replace errors → Home → Remove Rows → Remove Errors
4.	Optional: Fill missing values → Transform → Replace Values → Replace null with 0
5.	Home → Close & Load
________________________________________
6. Remove Duplicates
1.	In Power Query Editor: Home → Remove Rows → Remove Duplicates
o	Based on Order ID or combination of Product ID + Date + Salesperson
2.	Home → Close & Load
________________________________________
7. Calculated Columns (Total Sales, Profit)
1.	In Power Query: Add Column → Custom Column
o	Total Sales = [Units Sold] * [Unit Price] * (1 - [Discount])
2.	Home → Close & Load
________________________________________
8. Final Validation & Formatting
1.	In Excel: Select table → Ctrl + 1 → Number format
o	Numeric columns → Number with 2 decimals
o	Currency columns → Currency format
2.	Optional: Conditional Formatting → highlight negative Profit or unusual values
3.	Save the cleaned table


//Steps for Creating Slicer, Pivot table and chart

1) Insert  → Pivot Table. 
2) It shows a Create Pivot Table Tab, select the cleaned data table range → Ok. 
3) Then select the Fields in pivot table fields tab at right side of the window, as 
per the Below KPI’s. 
 Total Sales as per Region(Select Region in Rows and Total sales in 
Values). 
 Total units sold as per Region(Select Region in Rows and Units sold in 
Values). 
 Total Sales as per Payment Method(Select Payment Method in Rows 
and Total sales in Values). 
 Total Sales as per Products (Select Product Name in Rows and Total 
sales in Values). 
 Total Profit as per Region(Select Region in Rows and Total Profit in 
Values). 
 Total Profit as per Year(Select Year in Rows and Total Profit in Values). 
 Total Profit as per City(Select City in Rows and Total Profit in Values). 
 Total Sales as per Months(Select Date in Rows and Total sales in 
Values). 
4) Then Format the Pivot tables which is added as below, 
 To make values in Thousands or Millions: Click on any cell inside 
pivot table → Value field setting → Number format → Custom → 
Type(0,,"M" or 0,”K”) → ok. 
 Change color of the table: Select the pivot table →  Design → select 
the color in the color tab. 
 Insert Slicers: 
1) Select any Pivot table →  Insert →  Slicer → select the below KPI’s, 
 Region 
 Product Name 
 Payment Method 
 Years 
 Date 
 City 
 Product Category. 
2) Then Change columns size and number of columns needed by selecting the 
slicer → options → Buttons. 
 Insert Charts: 
1) Total Sales as per Region:  
 Select the Total Sales as per Region Pivot table → Insert → 
Recommended Charts → Pie → Doughnut. 
 Then select the doughnut chart which opens → Analyze → Field 
Buttons → Hide all. 
 Select the doughnut chart which opens → click + symbol in right top 
corner of chart → legend → right. 
 Select the doughnut chart which opens → click + symbol in right top 
corner of chart → Tick Data Lables & Chart Title. 
2) Total Sales as per Products:  
  Select the Total Sales as per Region Pivot table → Insert → 
Recommended Charts → Pie → Pie. 
 Then select the Pie chart which opens → Analyze → Field Buttons → 
Hide all. 
 Select the Pie chart which opens → click + symbol in right top corner 
of chart → legend → right. 
 Select the Pie chart which opens → click + symbol in right top corner 
of chart → Tick Data Lables → Ouside end → Tick Chart Title. 
3) Total Sales as per Payment Method:  
  Select the Total Sales as per Payment Method Pivot table → Insert 
→ Recommended Charts → Bar → 3-D Clustered Bar. 
 Then select the 3-D Clustered Bar chart which opens → Analyze → 
Field Buttons → Hide all. 
 Select the 3-D Clustered Bar chart which opens → click + symbol in 
right top corner of chart → Untick legend. 
 Select the 3-D Clustered Bar chart which opens → click + symbol in 
right top corner of chart → Tick Data Lables → Inside end → Tick 
Chart Title. 
4) Total Profit as per Region:  
  Select the Total Profit as per Region Pivot table → Insert → 
Recommended Charts → Column →  Clustered Column. 
 Then select the Clustered Column chart which opens → Analyze → 
Field Buttons → Hide all. 
 Select the Clustered Column chart which opens → click + symbol in 
right top corner of chart → Untick legend. 
 Select the Clustered Column chart which opens → click + symbol in 
right top corner of chart → Tick Data Lables → Center → Tick Chart 
Title. 
5) Total Profit as per City:  
  Select the Total Profit as per City Pivot table → Insert → 
Recommended Charts → Column → 3-D Stacked Column. 
 Then select the 3-D Stacked Column chart which opens → Analyze 
→ Field Buttons → Hide all. 
 Select the 3-D Stacked Column chart which opens → click + symbol 
in right top corner of chart → Untick legend. 
 Select the 3-D Stacked Column chart which opens → click + symbol 
in right top corner of chart → Tick Data Lables & Chart Title.  
6) Total Profit as per Year:  
 Select the Total Profit as per Year Pivot table → Insert → 
Recommended Charts → Line → Stacked line with Markers. 
 Then select the Stacked line chart which opens → Analyze → Field 
Buttons → Hide all. 
 Select the Stacked line chart which opens → click + symbol in right 
top corner of chart → Untick legend. 
 Select the Stacked line chart which opens → click + symbol in right 
top corner of chart → Tick Data Lables → above → Tick Chart Title. 
7) Total Sales as per Products:  
  Select the Total Sales as per Region Pivot table → Insert → 
Recommended Charts → Pie → 3-D Pie. 
 Then select the 3-D Pie chart which opens → Analyze → Field 
Buttons → Hide all. 
 Select the 3-D Pie chart which opens → click + symbol in right top 
corner of chart → legend → right. 
 Select the 3-D Pie chart which opens → click + symbol in right top 
corner of chart → Tick Data Lables → Best Fit → Tick Chart Title. 
8) Commonly, For all charts can format title and legend by, 
 Select the title or Legend → click Home → Fill color(For BG Color) 
→ B(For Bold the text). 
9) At last remove all grid lines by, 
 View → Untick Gridlines.
