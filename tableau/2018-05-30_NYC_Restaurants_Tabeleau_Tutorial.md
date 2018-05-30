# NYC Restaurant Data
Tableau Tutorial Cheat Sheet | Thursday, May 31, 2018

This tutorial uses the restaurant data we created as a class. [Download the data here!](TODO ADD LINK)


### Goals
- Discuss basic data cleaning and expansion
- Build a text table, scatter plot, and map in Tableau
- Maximize the usefulness of tooltips
- Create a dynamic dashboard using filter and URL dashboard actions
- Utilize a three-step process for layout design


## Data Prep

In preparing the data for our tutorial, we've done a bit of data preparation. Here's a recap of what we changed about the data structure and the data records. Before we made any adjustments, we created a copy of the data set first! As storage becomes cheaper and cheaper, there's rarely a reason to delete a data set. 

### Data Structure
- Removed Variables
	- Deleted the *Timestamp* and *Eatery Type* columns since there was very little information in these variables. 
	- Moved moved a few details in *Eatery Type* to *Description*
- Changed Variable Titles
	- Renamed *Name of Eatery* to *Restaurant* to make it more intuitive.
- Data Records
	- Removed the *test* record. This was never meant to be included in the data set. 
- Added New Variables
	- Long / Lat
	- Average Rating (Google)
	- Number of Reviews (Google)
	- Price (Google)

### Data Records
- Standardized Entries
	- Changed all *Your Name* entries to first names (some folks had entered first and last, some just first, some both on different records)
	- Changed all *Location* entries to standard addresses to allow Tableau to recognize the variable as a geospatial data type (some folks had entered neighborhoods, others had entered intersections, others had full addresses)
- Added Missing Data
	- Filled in missing *URL* fields (included Yelp pages for places without websites)















