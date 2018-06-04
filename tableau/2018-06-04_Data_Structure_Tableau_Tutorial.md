# Restructuring Data for Tableau
Tableau Tutorial Cheatsheet | Thursday, May 31, 2018

### Goals

- Recognize common data structure errors
- Identify variables vs data in spreadsheets designed for human eyes
- Pivot data in Tableau to create long and skinny data

### Messy Data Records vs. Unusable Data Structure

When we talk about cleaning a dataset, the changes we make usually fall into two categories: changes to the data structure or changes to the data records themselves. Think about where the 311 data got messy. Most of this came down to inconsistent categories, right? The taxonomy was inconsistent, and therefore the data was difficult to accurately aggregate. However, this messiness was restricted to the data itself (i.e., the content inside the cells). The data structure (i.e., the variables which dictated the columns) was consistent and structured for a computer to process. Today, we'll be talking about how to fix problems with this second category: data structure problems. Datasets are often structured for human eyes, which will not work when a computer program like Tableau tries to read the content. Let's look at a tiny text table to start, and then work through restructuring a real dataset from the United Nations. 


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
- Delete "Monday, Tuesday..." Row
- Save the changes in your Excel doc
- Open Up Tableau and drag that sheet into the display
- Select all of the column headings that start with a date (i.e., all of the columns except the first one)
- Right click and select pivot
- Now your data's all set! Create the viz ()
	- Part of the Day on Rows
	- Date (discrete day) on Columns, Date (day of the week) on Columns
	- Activity on Text and Color on the Marks Card


## Restructuring United Nations Population Estimates Spreadsheet

