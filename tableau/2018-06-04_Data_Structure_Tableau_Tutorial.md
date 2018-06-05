# Restructuring Data for Tableau
Tableau Tutorial Cheatsheet | Monday, June 4, 2018

### Goals

- Recognize common data structure errors
- Identify variables vs data in spreadsheets designed for human eyes
- Pivot data in Tableau to create long and skinny data

### Messy Data Records vs. Unusable Data Structure

When we talk about cleaning a dataset, the changes we make usually fall into two categories: changes to the data structure or changes to the data records themselves. Think about where the 311 data got messy. Most of this came down to fuzzy categories. The taxonomy was inconsistent, and therefore the data was difficult to aggregate with complete accuracy. However, this messiness was restricted to the data itself (i.e., the content inside the cells). The data structure (i.e., the variables which dictate the column structure) was consistent and ready for a computer to process. 

Today, we'll be talking about how to fix problems in this second category: problems with the structure of the data. Datasets are often designed for human eyes, which does not work well when a computer program like Tableau tries to read the content. We'll do a fair bit of restructuring by hand to ensure that you really understand what we're moving around. In the future, you will likely approach data cleaning like this with a program of some sort Let's look at a tiny text table to start, and then work through restructuring a real dataset from the United Nations. 


## The "Human Eyes" Spreadsheet

### Why are spreadsheets designed for human eyes?
- Often spreadsheets are built for human eyes to make creating the spreadsheet easy. 
- This is common with archival work, quantifiable self data, spreadsheets that are maintained by humans (which are especially common in offices with small datasets that aren't stored in databases)

### What's Wrong?
- Try hooking this spreadsheet up to Tableau: what's wrong?
- What are the actual variables we would need to make this visualization in Tableau?
	- Part of the Day on Rows
	- Date (discrete day) on Columns, Date (day of the week) on Columns
	- Activity on Text and Color on the Marks Card
- So what cells are the variables and what cells are the data? (hint: there are only three variables)
- With only three columns (one per variable), this will turn into a long and skinny dataset. It will be repetitive, which is exactly what we're looking for! 

### Cleaning by Hand
- Create headings for your three variables: date, part of the day, activity
- Triplicate the date field so that it appears as the first piece of data in three rows
- Do that for each date (if there are 9 days, this will make 27 rows in the data)
- Copy the Morning, Afternoon, Evening into the next columns next to each day's three dates
- Copy and paste the corresponding activities next to the appropriate dates and part of the day
- This will leave you with "long and skinny" data: only three columns with repetitive data that is Tableau ready

### Cleaning with Tableau
- Delete "Monday, Tuesday..." Row (this redundant data)
- Save the changes in your Excel doc
- Open Up Tableau and drag that sheet into the display
- Select all of the column headings that start with a date (i.e., all of the columns except the first one)
- Right click and select pivot
- Rename your column headings 
- Now your data's all set! Create the viz ()
	- Part of the Day on Rows
	- Date (discrete day) on Columns, Date (day of the week) on Columns
	- Activity on Text and Color on the Marks Card


## Restructuring United Nations Population Estimates Spreadsheet
Now let's look at a real example with much more data: population estimates from the U.N. Let's start at the [Population Division's World Population Prospects website here](https://esa.un.org/unpd/wpp/). Go to the Data tab and then to the Download Center. Download the first Excel spreadsheet called Total Population - Both Sexes. Open it up in Excel and you'll see clearly this is created for human eyes. If you try to point Tableau to this, it won't know which way is up. So let's clean! Make a fresh copy in your Excel workbook titled Cleaned Structure and take a good hard look at the table. What do you see that needs to be cleaned up to make this Tableau ready?

### Cleaning by Hand
- Cut the blue header and paste into a new sheet in the workbook called source (you don't want to get rid of important information like where your data came from while you clean)
- Delete all of the rows where the source header was
- Delete the row that says "Total Population, both sexes combined as of July 1 (thousands)" We'll come back to the thousands conversion in a bit
- Delete the World income developed population summaries (index rows 1-12)
- Now we need to breakout the "Region, Subregion, Country or Area" Column into the three separate variables it contains
- Insert a new column to the left and title it "Region"
- Insert a new column in between "Region" and "Region, Subregion, Country or Area" and title it "Subregion"
- Rename "Region, Subregion, Country or Area" to just "Country or Area"
- Now it's time to copy and paste. First, we'll fill in the Region column. Copy "Africa" and paste it in Column C until you reach Asia's subtotal line. Then copy "Asia" and paste it until you've reached Europe's subtotal. Rinse and repeat until you've filled in the "Region" variable for all of the 
- Using the same technique, we'll copy and paste the "Subregion" to fill in the data for column D
- Now delete all of the rows that are "Region" and "Subregion" subtotals. Once you've done that, you should have 233 records (or 234 rows including the column headers).
- Finally delete the "Index" and "Variant" columns, which won't be applicable in Tableau.

### Pivoting in Tableau

Now our spreadsheet has 233 records and 71 columns. The problem is that this dataset actually only has seven variables: Region, Subregion, Country or Area, Notes, Country Code, Year, and Population (in thousands). Seven variables should mean seven columns (not 71!) Right now we have *data* in the variables headings. That is, year data is sitting as a variable heading instead of sitting as a cell within a Year column. Imagine trying to pull "Year" to columns in Tableau to create a time line. You wouldn't have that data pill. You'd have 66 data pills, one of each year in the data set. So let's pivot the year columns so that it splits this information into the 2 variables it contains: Year and Population. 

- Open a new Tableau workbook and connect to your Excel spreadsheet
- Pull in the UN population dataset you've cleaned 
- Click the 1950 column header, hold down your shift key and select all of the remaining years by sliding over and selected 2015. 
- With all of the year columns selected, right click and select pivot.
- Now rename "Pivot Field Names" to "Year" and rename "Pivot Field Values" to "Population (by thousands)"
- Click on the "Abc" data type symbol above "Year" and change the data type to "Number (Whole)"
- Finally, let's create a population variable that's not in the thousands. 
- Right click in an empty spot in the data pane and select "Create Calculated Field..."
- Title your new variable: CALC: Population
- Drag the "Population (in thousands)" Variable into the text window and multiply it by a thousand. Your text box should look like this: [Population (thousands)] * 1000. Then say ok. You'll see your new variable show up in the Measures section of your data pane.

### Check Your Work
Always, always, always. When you finish a big restructuring job like this, you need to check that you've accomplished what you set out to do: restructure the dataset WITHOUT losing any of the data. Spot check that you've brought in all the records by comparing a few totals in Tabelau with the original UN spreadsheet. 

- Open up the original UN spreadsheet with the blue heading on the top
- Look at the world total for 1950 = 2,536,274,721 (cell F18)
- Now go back to Tableau. Put population on text and filter the viz by year to 1950. Do you get 2,536,274,721? If so, well done! Change the filter to another random year or two and ensure that your answer in Tableau aligns with the world population for that year in the UN table.
- Now add the Country or Area data pill to filter and spot check a few years by country. For example, if you set your filters to 1995 in Argentina, do you get a population of 34,994,814? 

### Word to the Wise: Look for the CSV or Server Connection
Head back over to the [Population Division's World Population Prospects website](https://esa.un.org/unpd/wpp/). Go to back to the Data Download Center and take a look at the top. Under "Major topic / Special Groupings" you'll CSV format. This is the format we would have wanted! When you see data formatted for statistical software, this is what you're after. I've made this mistake before, moving too quickly looking for data, and not realizing that both a "human eye" version and "computer" version are being offered. If you download one of these datasets and take a look, you'll immediately see the difference. They're Tableau ready. 


















