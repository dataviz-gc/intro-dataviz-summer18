# Joining Multiple Tables in Tableau
Tableau Tutorial Cheatsheet | Tuesday, June 5, 2018

### Goals

- Understand the basic reasoning behind relational databases
- Identify the differences between a inner, left, right, and outer join
- Build a dataset by joining several tables in Tableau

### What Are Joins?
Joins let us connect separate tables of data that share a common variable. We often store data in smaller, separate tables that just contain information about one topic. This makes the data much easier to maintain. The table might only contain a few variables, but if it shares a piece of information with another smaller table, like a data, ID, or location, we can connect multiple tables to create a more robust dataset by establishing a join on that shared variable. 

For example, let's say you have a table of all the emails you've received over the past year. It has the email's subject line, the time and date it was sent, how many times you opened it, whether it was marked as important, and so on. This table includes the sender's email address, but doesn't have any additional information about that person. Now imagine you have a second table, perhaps exported from your contacts app, the included email addresses, first and last name, job position, etc. A join would let you connect the first table with your emails with the second table from your contacts. The email address would be the variable you would join on, and it would create the bridge between the two tables to create a more comprehensive dataset. 

Let's first look at a small example with just a few records per table to understand the four different types of join, and then move on to a much larger tables from the UN that require us to create joins on multiple variables. 

## Person, Pets, Jobs: Tiny Example
Our first example will use a few tiny tables about my family: a Person Table, a Pet Table, a Pet Nickname Table, and a Job Table. 


### Four Types of Joins
Joins come in four different flavors: inner join, left join, right join, and full outer join. Each of these joins is created by using a common variable that is found in both tables. However, each of these joins creates a different connection (or sets up a different relationship) between the two tables. Let's use the Person and Pet tables to see how each of these joins works. 


#### Inner Join
**An inner join keeps only the records that appear in both tables.**

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/join_inner.png)

In Tableau's Data Source environment, connect to our Excel spreadsheet and drag the Person Table into the orange area. You'll see the Person Table appear below with just 4 variables: Person ID, First Name, Last Name, and Birth Date. There are also just 3 records, one for Sally (my mom), Erin (me), and Emma (my sister).

Now let's join the Pet Table to the Person Table. Drag the Pet Table into the same space where the Person Table already sits. Notice that Tableau immediately connects the two tables with an Inner Join represented by the venn diagram with just the center filled in. If you click on that venn diagram icon, you can see that Tableau has recognized that the Person ID is the same in both tables and has established the join on that variable.

Now look that the data below. My sister Emma has disappeared. My mom Sally has two dogs, I have one dog, but my sister does not have any pets. An inner join only keeps records that appear in both tables. Since Emma's Person ID doesn't exist in the Pet Table because she doesn't have any pets, her record in the Person Table is dropped. 

You'll also notice that the dog Cody (who belongs to my mother-in-law) has disappeared as well. Since my mother-in-law isn't in the Person Table, Cody's record is dropped as well. 

Inner joins are very common and can be a great way to limit your dataset to just records that appear in both places. For example, in our email example before, an inner join between your email table and contact table would drop all the emails for which you didn't have a contact records, and would also drop all contact records who hadn't sent you an email. 


#### Left Join
**A left join keeps all the records in the primary (left) table and drops unmatched records in the secondary (right) table.**

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/join_left.png)

Now click on the venn diagram icon in Tableau and change the join type from an inner join to a left join. My sister Emma reappears. You'll see that Tableau has added *null* in each cell for the Pet Table variables since there is no information corresponding to her in that table since she doesn't have a pet. However, Cody still doesn't appear because he doesn't have a corresponding record in the Person Table.

A left join holds on to all of the records in the primary table on the left (all the Person records) and the looks to the right table for any corresponding information. Left joins are also common. Continuing with our email / contact example, a left join would hold onto all of the email records, match up any corresponding contacts, and just create null values for anyone who wasn't in your contacts. Anyone who was in your contacts but didn't send you an email would be dropped. 


#### Right Join
**A right join keeps all the records in the secondary (right) table and drops all unmatched records in the primary (left) table.**

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/join_right.png)

A right join functions just like a left join in reverse. Change the join in Tableau and you'll see Emma disappear and Cody appear. All the records in the secondary table on the right are kept and matched up to any corresponding records in the left table. 

Right joins are much less commonly used, mainly because if you actually cared about the table on the right more than the table on the left, you'd drag that table out first and create a left join instead. In our email/contacts example, a right join would create a dataset with all of your contacts and would only keep the emails for which you had a contact record. 


#### Full Outer Join
**A full outer join keeps all the records in both tables.**

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/join_full_outer.png)

Last but not least, change the join type to full outer. You'll see the entire venn diagram icon filled in. All records from both tables will be kept and any missing values will just be filled in with *null*. This means that Emma from the Person Table appears even though she doesn't have any pets, and Cody from the Pet Table appears even though he doesn't have a person in the table. In our email example, this would mean all of your emails and all of your contacts would be included in the dataset. 


### Connecting Multiple Tables
Now let's connect multiple tables. You'll see that as we add more tables, the number of records will increase.

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/join_multiple_tables.png)

- Change the join between the Person Table and the Pet Table back to a Left Join (Cody will disappear). This will leave you with 4 records (Sally appears twice because she has two dogs.)
- Drag the Pet Nickname Table out. Tableau will connect it to the Pet Table on the Pet ID. You'll see that it established an Inner Join, which propagated back to the Person Table and made Emma disappear again. 
- Change the join between the Pet Table and the Pet Nickname Table to a left join. Emma will reappear. You will now have 7 records (six nicknames plus Emma's empty record).
- Now drag in the Job Table. Tableau will connect the Job Table to the Person Table on the Person ID with an Inner Join. Since all three people appear in both tables, any of the join types will give you the same dataset with 20 records. 

When you're analyzing your data, you need to remember that you've created duplications in your dataset. Go to Sheet 1, pull Pet Name to Text, and do a simple count (dropdown menu on Pet Name > Measure > Count), you'll see 18 pets. There are not 18 pets in this data set, but the three dog names repeat throughout the dataset 18 times. Change the Measure to Count Distinct and you'll see 3 again. Disaggregating in this way is important when you've created redundancies in your data with your joins. 

### Maintenance and Flexibility of Smaller Tables

The dataset you've created now has 15 variables. Think of updating this dataset once someone gets a new pet, new job, or a dog gets a new nickname. It's much easier to just go to a smaller table with only that information and add a few new pieces of information than it would be to update all of the other unrelated information in this bigger table.

It also makes your data much more flexible. Let's say you just wanted to look at the Person and the Job tables. You wouldn't have the mess with the Pet data at all. Smaller tables like this make it much easier to only work with the data you need.  

## UN Data: Joining on Multiple Variables

