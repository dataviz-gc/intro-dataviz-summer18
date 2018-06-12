# Treemaps & Dispersion Plots: Visualizing Text
Tableau Tutorial Cheatsheet | Tuesday, June 12 and Wednesday, June 13, 2018

### Goals

- Understand the scope of data prep for a text analysis project
- Identify when to use Tableau in a project of this size
- How to build and when to use a treemap
- Incorporating table calculations into tooltips
- How to build dispersions plots
- Visualizing an entire data set at once

## Le Morte D'Arthur
As we explore treemaps and dispersion plots, we will use data scraped from the medieval book, Le Morte D'Arthur. The book was written by Thomas Malory and then heavily edited by William Caxton after his death. Caxton printed and published the book in 1485. In the briefest summary, the book gathers up the many stories that had proliferated around the Arthurian legend during the middle ages. [Learn more about the book here.](https://en.wikipedia.org/wiki/Le_Morte_d%27Arthur)

### Research Questions
1. How many characters are actually appear in this book?
2. Which characters dominate which parts of the book?
3. How heavily did Caxton change the book's structure?
4. Do Caxton's summaries accurately represent the characters that appear in the chapters?

### Scraping the Data
This is not a class about text analysis, but the topic has come up repeatedly. The purpose of briefly discussing the process of scraping the data for this visual analysis is to help delineate when Tableau is the right tool for the job and, more importantly, when it's not. The data set needed to be assembled outside of Tableau. My husband and I created an entirely separate program in Python to scrape the data for these visualizations. We had to transform [the text](https://www.gutenberg.org/files/1251/1251-h/1251-h.htm#link2HCH0015) into [this dataset](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/data/week3/Le-Morte-dArthur-Data.xlsx). This work is not what Tableau is for. Tableau wants to sit on top of a clean, well-structured dataset. It is not a tool for creating a data set nor a tool for intense data cleaning. 

Here were the variables we wanted to have in our dataset:
- Book Number
- Chapter Number
- Character's Name
- Word Location
- Writer's Name

Here are some of the challenges we had to solve:
- How to identify names (vs other capitalized proper nouns, like places)
- How to capture who was writing (Malory's text vs Caxton's headers)
- How to create a the hierarchy of chapters nested in books

Consider how much we know glancing at the text that a computer wouldn't recognize without being told (ex: chapters go into books, the editorial context of this piece, etc.) Think about what we understand that has to be made explicit. Consider how much cutting, cleaning, and framing has happened to create this dataset. Think of the data that's been lost. Consider what would happen if you tried to attach Tableau to the text file.

## Treemaps
Treemaps work well when bar charts tend to start to fail. Usually Treemaps take an area (often a rectangle) and break it into chunks based on what percentage of the total those chunks take up. For example, if you made a treemap of the world population and broke it up by country, the United State population was approximately 4.3% of the world population (using 2015 UN estimates), and therefore the piece of the treemap for the United States take up 4.3% of the total area of the treemap. 


### Make a Bar Chart First
Let's start with a bar chart to see where it works and where it doesn't.
- Drag Character Name to rows
- Drag Number of Records to columns
- Drag Writer Name to Filters and just keep Malory's writing for now
- Rank these names if you'd like by adding another Number of Records after Charter Name on Row
- Change this Number of Records pill to discrete
- Then change the pill to a Quick Table Calculation and choose Rank

Note the following things:
- Launcelot and Tristram occur more often than Arthur (adulterous relationships)
- False positives (how are these different: La, Day, God)
- There are 240 marks (which means the program identified 240 characters)
- Change the view from Standard (dropdown menu by the pin icon) to Entire View

That's not exactly a helpful visualization. And when you see a mess like that, it's usually time for a treemap. The treemap will help us see the big characters without losing track of all of the smaller characters. 

### Now Try a Treemap
Make a new sheet and let's use the same information in a treemap. 
- Filter your visualization to just Malory's writing
- Drag Character Name to Detail
- Drag Number of Records to Size

And that's it! A treemap is very easy to make in Tableau. However, tooltips and labels can be very helpful to a viewer who has never seen a treemap before. Let's clean those both up to make this visualization more clear. 
- Add Number of Records to Tooltip and turn it into a Rank using the Quick Table Calculation
- Add Number of Records again to tooltips and turn it into a Percent of Total using the Quick Table Calculation
- Clean up the format of your tooltip. Consider using a sentence like this: <Character Name> (<Rank of SUM(Number of Records)>) The name <Character Name> occurs <SUM(Number of Records)> times, which accounts for <% of Total SUM(Number of Records)> of all the character names mentioned.
- Now add Character Name to Label
- Also add your Quick Table Calculation for Rank to Label as well

### Small Multiples
Finally, if you want to see how this treemap changes during different books, show the Malory's Book data pill and filter it just to the first book of eight. Duplicate the treemap to create eight visualizations that are all identical except they're each filtered to just one book. Now drag them each into a single dashboard (lining them up so they progress from book 1 through 8). Once you've adjusted the tiles, add a highlight dashboard action on Character Name. (Dashboard Menu > Action... > Add Action > Highlight... > OK). Now your end user can easily hover over any single character's name and see how dominant they are throughout the eight different books.

## Dispersion Plots (6/13/18)







