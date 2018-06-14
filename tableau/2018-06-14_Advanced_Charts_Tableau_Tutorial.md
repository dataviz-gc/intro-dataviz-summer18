# Advanced Chart Types: Bump Chart, Donut Chart, Bullet Graph, Slope Chart
Tableau Tutorial Cheatsheet | Thursday, June 14, 2018

### Goals

- Learn how to create more advanced chart types in Tableau
- Build a bump chart, donut chart, bullet graph, and slope chart

## Bump Chart
We'll use the [UN Population Estimates dataset](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/data/week3/Population-Estimates-by-Country-1950-2015-United-Nations.xlsx) for today's visualizations. We'll start with the bump chart. Bump charts do a great job of representing changes in rank over time. You'll often see bump charts in sports data showing how different teams have lead or fallen behind in their division over the course of a season. In our case, we'll build a bump chart showing which countries have been the most populous over time. 

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/Bump_Chart.png)

How to build a bump chart:
- Drag Year to Columns 
- Drag Population to Rows
- Add Country or Area to Color
- Change the Population pill to a Rank Quick Table Calculation (this will look crazy)
- Change the Compute Using on the Population pill from Table(Across) to Country or Area
- Right click on the Y Axis (rank of population) and select Edit Axis
- Uncheck Include Zero and Check Reversed
- Click the dropdown menu on Sum(Population) on the rows shelf and select Show Filter
- Adjust the filter to only show the top 20 countries
- Make the Size of each line a bit smaller
- Add small circles marking each year by clicking on Color and selecting the middle Markers option under Effects

## Donut Chart
A donut chart is a good alternative to a pie chart. By hollowing out the middle, you create a space to add context with a label. Limit the number of categories represented in a pie or donut chart to three or four. In my personal opinion, using just two items is best. Showing the percentage something is complete is a great option. 

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/Donut_Chart.png)

How to build a donut chart:
- Create a new Calculated Field named "CALC:0" and just enter the number "0" in the text box. (If you look at your data source now, you'll see that a column with just 0 has been added to every record.)
- Drag your new CALC: 0 variable to rows and then drag a second CALC:0 variable, so that you have two of the same data pills sitting side by side on the rows shelf. 
- Click the dropdown menu on the second CALC:0 and select Dual Axis. This creates a combination chart and changes your Marks Card shelf to have three panes, one controlling both circles, the other two controlling one circle independently.
- Right click the right axis and select Synchronize Axis
- Click on the middle marks card and change the Mark Type from a circle to a pie.
- Click on the bottom marks card. Change the color to white and make the size of this circle a bit smaller. You now have a donut!
- Click on your pie marks card (the middle one) again. You'll see that you have a new option here: Angle.
- On the pie marks card, drag Country or Area to Detail. Hover over your donut and now you will see one even slice for every country in the data set. 
- Click on Color and add a white border so that you can easily see each slice of the pie. 
- Before we tell Tableau how big to make each of those slices, let's filter to just 2015 using the Year variable and just to Africa using the Region. 
- Now let's size each slice of the pie based on how big the population is. Drag Population to Angle. 
- Order the slices from biggest to smallest by clicking the dropdown menu on Country or Area on the marks card and changing the sort to Descending by a Field. Select Population and make sure the aggregation is set to sum. 
- Now let's break out the donut chart into a separate donut chart for each subregion in Africa by dragging Sub-Region to Columns. 
- You can change the view from Standard to Entire View and expand the sizes of your donuts using the size button on the Marks Card.
- Finally, you can add a label in the middle of your donut. Click on the third marks card and pull Subregion on to Label. Click on label and change the alignment to center it vertically. 
- You can also add the total population or the distinct count of countries, or something else to this center area.
- NOTE: This is an example of how to build a donut chart, but I'll reiterate that this is not the ideal type of data to visualize this way. As you can see in the Tableau workbook, a treemap or a bar chart actually displays this information much better.


## Bullet Graph
A bullet graph is just a bar chart with a small line sitting somewhere along the X axis that marks a benchmark, threshold, or comparison of some sort. This is a common chart for comparing progress towards a goal. With this dataset, we'll build a bullet graph that compares populations from 2000 to 2015.

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/Bullet_Graph.png)


## Slope Chart
A slope chart cuts out the middle of a line chart and just shows the absolute increase or decrease of the first and last point in time. In our case, we'll look at the change in population from 2000 and 2015. This is another way to visualize the same information we examined with our bullet graph above.

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/Slope_Chart.png)

