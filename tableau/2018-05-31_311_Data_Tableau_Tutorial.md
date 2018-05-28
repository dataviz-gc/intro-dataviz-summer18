# 311 Data 
Tableau Tutorial Cheatsheet | Thursday, May 31, 2018

## Goals

- Access data through a public repository
- Explore a data set using its data dictionary
- Organize the variables into folders
- Create a Table Calculation, a Hierarchy, and a Set
- Create a Heat Map
- Working with Data Parts in Tableau




## NYC Open Data
[NYC Open Data](https://opendata.cityofnewyork.us/) > Data > Popular Datasets > [311 Service Requests from 2010 to Present](https://nycopendata.socrata.com/Social-Services/311-Service-Requests-from-2010-to-Present/erm2-nwe9)

### Questions to Ask
- How is the data collected?
- How big is the data set?
- What variables are collected?
- How is the data structured?

### How to Connect to the Data

There are two fundamental types of data connections you can set up. 

- Static Export (Excel, CSV)
- Live Connection (API, [OData](https://support.socrata.com/hc/en-us/articles/115011744048))

## Organizing the Data Pane

### Create Folders
Let's group our variables by theme to make them easier to work with and better understand what's here. This is where the data dictionary comes in. 

### Explore a Variable with a Bar Chart
- Drag *Complaint Type* to Rows
- Drag *Number of Records* to Columns
- Sort bars in descending order
- Add rank by dragging *Number of Records* to Rows (you'll get an unwanted scatterplot)
- Change this second *Number of Records* to a discrete (instead of continuous) variable by changing the toggle on the dropdown menu
- Also on the dropdown menu, add a the *quick table calculation* rank (you'll see a delta show up on the data pill)

#### Noise (Taxonomy Inconsistencies)
- Notice the inconsistencies with noise categories
- Show the filter for *Complaint Type*
- Change the filter type to wildcard search (10 different noise categories)
- There's even a category simply called *Complaint* 

#### NONCONSTR (Unclear Category)
- What is NONCONSTR? (is this just not construction?)
- Filter the *Complaint Type* to just "NONCONST"
- Breaking it down by borough doesn't tell us anything
- Breaking it down by *Descriptor* does

#### Compliments? Really?
- Filter the *Complaint Type* to just "compliments"
- Breaking it out by *Descriptor* doesn't tell us much
- Add *Unique Key* to Detail
- Add *Resolution Description* to Tooltip
- All rerouted to appropriate service or department

### Create a Hierarchy
- Drag *Descriptor* on top of *Complaint Type* in the data pane
- Name and then create your hierarchy
- Now go back to your original bar chart and expand the hierarchy with the small plus sign that's now on the *Complaint Type* data pill


### Create a Set

- Entire View of bar charts (long skinny tail)
- Create Rank: table calculation off number of records
- Set of Top 10
- Remove Complaint Type > More than half of the complaints fall in the top 10 group



## Creating a Heat Map

- weekend pattern: could be people are less likely to complain on the weekend OR is it possible that there's a pattern to the way the data's collected?
- add top 10 set filter
- add complaint type filter: 
1. Blocked Driveway: isolated incidents?
2. General Construction: weekends are light, summer was actually lighter
3. Heating: weather dependent
4. Noise: now we have a weekend complaint
- duplicate sheet: breakdown by borough




