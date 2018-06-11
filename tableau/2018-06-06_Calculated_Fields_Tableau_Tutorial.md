# Creating Calculated Fields and Parameters in Tableau
Tableau Tutorial Cheatsheet | Wednesday, June 6 and Thursday, June 7, 2018

### Goals

- 
- String Manipulation
- If / Then Statements
- 



## Bar Chart vs. 100% Bar Chart



## Calculated Fields

### String Manipulation
LEFT: create alphabet


### IF/THEN Statement

IF/THEN Statements, female and male records
Duplicating Pills

### Basic Math

sum(female occurrences)/sum(occurrences) > will give the % of the occurrences for each name that are female


### Boolean

Finding the interesting data points: true or false (or null)

[CALC: Percent Female] > .1
AND
[CALC: Percent Female] < .9

TOMORROW

### Area Chart vs. 100% Area Chart



### Double Area Chart

- Duplicate 100% area chart filtered to Morgan
- Drag Sum(Occurrences) to rows and set it *in front of* the percent of total Sum(Occurrences). (You can tell the difference by the small delta on the second pill, which tells you that there is a table calculation happening on that piece of data.)
- Now drag Name in front of both of these Sum(Occurrences) pills. It will only show Morgan to start.
- Click on the dropdown menu on the Name pill, and select Show Filter. 
- Let's add a few more names. Try Jordan, Alexis, Johnnie, and Kelly. 
- You'll notice this broke your 100% Area Chart. Click that data pill's dropdown menu and change the Computing Using option for your table calculation to Pane(down). This will create a 100% area chart for each name.