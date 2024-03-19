# Maven Cycles Sales and Profit-Dashboard

### Dashboard Link : https://www.novypro.com/profile_projects/ayan-malik

## Problem Statement

Maven Cycles is huge organization they have Multiple Products category e.g. Bike, Accessories, Clothing etc so this dashboard helps the Maven Cycles understand their Bussiness better. 
It helps the Maven Cycles to know some import Points about their Bussiness which are following-

* Sale by Category.
* Profit by Countoey.
* Revenue by Contary.
* Profit Marging by Product.
* Forcasting of Profit.
* Root Couse Analysis of Revenue.
* Top 20 Products that beling Sold, Ordered and Genragting Profit by Country, date and Category.
* Sale By Country and Category.
* Profit Analysis by Year and Category/Country.
* Profit Marging By Product Name/Prodcut Category/ Region/Continent/Country. 
* Key Influencer.
* Product Sold By Country.


Through Above Points Maven Cycles can Understand their customers are satisfied with their Products. Through different KPIs, 
they get to know their improvement area, & thus they can improve their Products by identifying these area. 
thus since by using this dashboard they have identified their Bussiness, they can further work on factors responsible for Losses.




### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors & empty values were present in Dataset.
- Step 5 : Since dataset is not strctured in Proper way so Aplied steps Like Promoted Headers, Added and Removed Columns, Renamed Columns, Added Conditional Columns
 	   and Column From Examle etc.
- Step 6 : Calender Table Has three differnt Columns but there no name Mentioned for the Columns so Saprated by Comma as Delimeter.
- Step 7 : Since the dataset contains various Tables, thus in order to Create relationships used Star Schema 
          but Product Category was not in poper manner so Connected them by Chain same as Snowflake Schema.

![Star Schema](https://github.com/ayanmalik/Maven-Sales-and-Revenue/assets/15996271/a854821b-392e-43f4-8ed3-78e03b6b82b5)

![Snowflake](https://github.com/ayanmalik/Maven-Sales-and-Revenue/assets/15996271/35fe7f11-a024-4fe5-af42-df00867b37df)


- Step 8 : In the report view, under the view tab, theme was selected.

*** Visuals And Tabs***
### Executive View --
- Step 9 : Added 3 KPI Card Visual to show Total Revenue, Total Profit, Profit Margin.

![KPI Card](https://github.com/ayanmalik/Maven-Sales-and-Revenue/assets/15996271/5e549f6c-4e11-41bb-a2a8-41d20d7d22f7)

- Step 10: Added Map Visual to show revenue by Country.

![Map Visual](https://github.com/ayanmalik/Maven-Sales-and-Revenue/assets/15996271/34f8af7c-f571-4549-89f2-f24b597f8cd9)

- Step 11: Added Table Visual to show TOP 20 Product by Name, Total number of Order, Revenue by Product and Profit Margin by Product.

![Table Visual](https://github.com/ayanmalik/Maven-Sales-and-Revenue/assets/15996271/6545269b-c893-45aa-90fe-9c36cddddd77)

- Step 12: Added Donut Chart Visual to show product Category.
![Donut](https://github.com/ayanmalik/Maven-Sales-and-Revenue/assets/15996271/8b6a3efc-3dfc-4fc5-bb17-3f67eebad906)

- Step 13: Added Line chart Visual to show Profit By Period. Also used Analytics Feature to show Trend Line and Forcastig for the Upcoming 3 Months of Profit.

![Line chart](https://github.com/ayanmalik/Maven-Sales-and-Revenue/assets/15996271/f5951665-c8e5-4855-ae3b-1906ffcb7ef6)

- Step 14: Visual filters (Slicers) were added as a Date Filter Using Bookmark Feature as well to show jump on Desire date.

![Date Filter](https://github.com/ayanmalik/Maven-Sales-and-Revenue/assets/15996271/2e73f7d3-09a7-43ac-9a91-37472754fc8f)

- Step 15: Added Two Button to perform action to Reset and To jump on 1H 2020 Date Using Bookmark Feature.

![Button](https://github.com/ayanmalik/Maven-Sales-and-Revenue/assets/15996271/27725805-1132-4fa4-acb9-c07212ec2256)

- Step 16: Added Two Slicers for the Product Category and for the Continent.

![Sub Category  Slicer](https://github.com/ayanmalik/Maven-Sales-and-Revenue/assets/15996271/5dc2dd3e-1859-41c5-a7a1-c510859c2ff3)
![Continent Slicer](https://github.com/ayanmalik/Maven-Sales-and-Revenue/assets/15996271/c0d7c409-bbf4-4d1d-b7da-338c35a166ec)

- Step 17: Used Drillthrough Feature to Filter out the Revenue by Country for the root couse Analysis Using AI Visual (Decomposion Tree).

![Drill Through](https://github.com/ayanmalik/Maven-Sales-and-Revenue/assets/15996271/a298f80f-2813-4372-8b70-23b97e7a341d)

### Profit View --
- Step 18: Waterfall Chart Visual was added on Prot Tab to show profit break down by  Period and Category.

![Drill Through Profit](https://github.com/ayanmalik/Maven-Sales-and-Revenue/assets/15996271/ab4dd466-16f6-494c-b70c-6bf5129a849e)

### Profit Margin --
- Step 19: Added Clustered Bar chart Visual to profit Marging by Different Category Using Filter Parameater. End User can see Profit Marging Through Selecting Different filter Options.

![Feald Parameater](https://github.com/ayanmalik/Maven-Sales-and-Revenue/assets/15996271/1b1db767-a5b8-4373-86c8-f3c75a790f15)


### Sale Influencer --
- Step 20: Added Tab to show Top Segment Products by Using AI Visual(Key Influencer).

![Key Influencer AI Visual](https://github.com/ayanmalik/Maven-Sales-and-Revenue/assets/15996271/c8a1fd42-5df3-4188-aae1-b12e213cece6)

### Sale By Groups.
- Step 21: Added a Column Chart Visual to show to sale by Using Grouping Feature.End User can see sale by Desired Group.
	
![Grouping Bar](https://github.com/ayanmalik/Maven-Sales-and-Revenue/assets/15996271/7eb832ba-8ecc-4496-b159-440d6f808983)

Didn't use any calculated Column so that Model size should not be Increase.

        
- Step 22 : New measure was created to calculate To Total Revenue

Following DAX expression was written for the same,
        
    Total Revenue = 
    SUMX(
        'Maven Cycles Sales',
        'Maven Cycles Sales'[Quantity Sold] *
        RELATED(
                'Maven Cycle Products'[Unit Price]
        )
    )
A KPI visual was used to represent Total Revenue.

![Revenue](https://github.com/ayanmalik/Maven-Sales-and-Revenue/assets/15996271/690fe6ae-cee5-4d13-810f-9681817bd282)

        
 - Step 23 : New measure was created to find  % of Profit
 
         DIVIDE(
                 [Profit],
                [All Profit]
                )

 
 A KPI visual was used to represent this perecntage.
 
 ![Profit](https://github.com/ayanmalik/Maven-Sales-and-Revenue/assets/15996271/025aa092-eb72-4ecf-9cfe-5b937c160063)
 
 
 
 - Step 24 : New measure was created to calculate total Profit Margin
 
 Following DAX expression was written to find Profit Margin.

        Profit Margin = 
        DIVIDE(
             [Total Revenue]-[Total Cost],
            [Total Revenue],
             "N/A"
         )
 

 A Table visual was used to represent this total Profit Maring.
 
 
![Profit Margin](https://github.com/ayanmalik/Maven-Sales-and-Revenue/assets/15996271/9d5ce49f-7d06-4727-882b-359dba6d5f4e)
 
 - Step 25 : New measure was created to calculate Last Month Profit.


        Last Month Profit = 
         CALCULATE(
                [Profit],
                DATEADD(
                    'Maven Cycles Calendar'[Date],
                    -1,
                    MONTH
                )
            )


 - Step 26 : New measure was created to calculate total Last Month Profit Margin.

        Last Month Profit Margin = 
                    CALCULATE(
                            [Profit Margin],
                        DATEADD(
                            'Maven Cycles Calendar'[Date],
                            -1,
                            MONTH
                        )
                    )

 - Step 27 : New measure was created to calculate Last Month Revenue.

        Last Month Revenue = 
                    CALCULATE(
                            [Total Revenue],
                        DATEADD(
                            'Maven Cycles Calendar'[Date],
                            -1,
                            MONTH
                            )
                        )

 - Step 28 : New measure was created to calculate Mid Range Revenue

        Mid Range Revenue = 
                    SUMX(
                        FILTER(
                            'Maven Cycle Products',
                            'Maven Cycle Products'[Price Range]= "Mid"
                            ),
                            [Total Revenue]
                    )

 - Step 29 : New measure was created to calculate Quantity Sold (Stock Date).

        Quantity Sold (Stock Date) = 
                        CALCULATE(
                                [Quantity Sold],
                            USERELATIONSHIP(
                                'Maven Cycles Sales'[Stock Date],
                                'Maven Cycles Calendar'[Date]
                            )
                        )



 - Step 30 : New measure was created to calculate Quantity Sold YTD.

        Quantity Sold YTD = 
                 TOTALYTD(
                        SUM(
                            'Maven Cycles Sales'[Quantity Sold]
                            ),
                            'Maven Cycles Calendar'[Date]
                        )

 - Step 31 : New measure was created to calculate Total Cost.

            Total Cost = 
                  SUMX(
                    'Maven Cycles Sales',
                    'Maven Cycles Sales'[Quantity Sold] *
                  RELATED(
                      'Maven Cycle Products'[Unit Cost]
                    )
                )


 - Step 32 : New measure was created to calculate All Profit.


        All Profit = 
            CALCULATE(
                    [Profit],
                 ALL(
                 'Maven Cycles Sales'
                 )
             )
 - Step 33 : The report was then published to Power BI Service.

# Snapshot of Dashboard (Power BI Service)

![Published on BI Services](https://github.com/ayanmalik/Maven-Sales-and-Revenue/assets/15996271/46cb17b1-b517-43da-9537-9b7056429cd1)

 # Report Snapshot (Power BI DESKTOP)

![BI Desktop](https://github.com/ayanmalik/Maven-Sales-and-Revenue/assets/15996271/9768ba93-b7d0-49cd-9849-189a6edefde8)

# Insights

A Multiple page report was created on Power BI Desktop & it was then published to Power BI Service.


 
### Some other insights By Time Intellingence



### [1] Summary


    Total Revenue = $251538599.

	Total Cost   = $126123609.27
  
	Total Mid Range Revenue = $61283780.17

	Total profit = $125414989.89
 

### [2] Profit And Revenue By  Category.

![BY Category](https://github.com/ayanmalik/Meven-Cycle-Sales-And-Profit/assets/15996271/2ca55a7f-f690-4964-b948-39714bb17c82)


### [3] Top 10 Sold Products.

![Top 10 Prod](https://github.com/ayanmalik/Meven-Cycle-Sales-And-Profit/assets/15996271/fab7fe8c-7fc8-402c-ab38-3a8e0f603263)

### [4] Insights By Conutry.


![IN By Country](https://github.com/ayanmalik/Meven-Cycle-Sales-And-Profit/assets/15996271/bb13a955-28f5-4ba4-9354-a87a5ad1ccf5)

### [5] Last Months Insights.

![Last Month's Insights](https://github.com/ayanmalik/Meven-Cycle-Sales-And-Profit/assets/15996271/8f372142-ea1b-4eb8-b433-2ccdb29deee1)

    
    

 
