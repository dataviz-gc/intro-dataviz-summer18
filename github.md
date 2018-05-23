# Tech Set Up

Throughout this course we will build data visualizations using Tableau and share what we've built using GitHub. This tutorial will walk you through setting up each piece of our technology pipeline. 

*TODO Insert Pipeline Graphic Here*

## STEP 1: Downloading Tableau Software

### What's Tableau?
We will build all of our data visualizations using Tableau Software. Tableau is a leading data visualization tool. Its drag-and drop-interface allows users to create interactive and dynamic data dashboards without coding. As visual analytics continues to grow, Tableau has become increasingly popular in corporate, nonprofit, and government sectors. 


Tableau Desktop comes in two flavors. There's a public version that only allows you to save your work publicly. This the version we will be using throughout the course. However, Tableau Desktop also comes in a professional edition that allows you to save your work locally. This is essential for any proprietary work, which is how Tableau makes their money. This edition is FREE for all students and instructors. You can learn more about Tableau for Students [here](https://www.tableau.com/academic/students).

#### How to Download the App
To start building out our technical pipeline, download Tableau:

- Go to [Tableau Public](https://public.tableau.com/en-us/s/)
- Enter your email in the box
- Click download the app
- Install the app on your computer
- Launch Tableau


*TODO Insert downloading screenshots here*


### Build Your First Visualization
Now you're ready to build your very first visualization! Let's start with something simple. Wel'll look at how populations in different regions around the world have changed over time. First, we'll connect Tableau to a dataset from the United Nations and then we'll build a line graph.

#### How to Connect Tableau to a Data Set

- Download this Excel spreadsheet
- Go back to Tableau where you should see a blue panel on the left title *Connect*
- Click on *Microsoft Excel*, select the *U.N. Population Estimates*, and click *Open*
- Drag the *Population Estimates UN* sheet into the center space titled *Drag Sheets Here*
- Click *Sheet 1* in the orange box in the bottom left corner


*TODO Insert connecting data screenshots here*

#### How to Build a Line Graph
On the left side of your screen, the variables in the data set have been split up into dimensions (descriptive pieces of data, like the name of a country or the region where it's located) and measures (pieces of data you'd do math on, like the population). Let's build a line graph that breaks down the world's population by region for the second half of the 20th century. 

- Drag *Year* to Columns
- Drag *Population* to Rows
- Drag *Region* to Color
- Click the dropdown menu that appears when you hover of the *Year* data pill
- Select *Show Filter*
- Adjust the Year Filter from 2015 to 2000
- Double click on *Sheet 1* and title your sheet *Population by Region*

*TODO Insert line graph screenshots here*


## STEP 2: Creating a Tableau Public Profile

### What's a Tableau Public Profile?
Congratulations! You've just created your very first interactive visualization in Tableau. Now you want to be able to share it with the world. A Tableau Public Profile provides a platform to publish and share your visualizations. It retains all of the aspects that make Tableau's output unique, such as the dynamic filters (like the year filter you added to your line chart above) and the interactive tooltips (those little text boxes that pop up when you hover over a given data point). 

Tableau Software hosts the server and each published visualization comes with a tiny snippet of *embed code* that allows you to embed your visualizations in other platforms, like a website. This is what will allow our GitHub repository to access our visualizations (that's coming up in just a few steps!) Note that when you save your work to your Tableau Public Profile, your visualizations will be available for anyone to access online. *Do NOT publish confidential data to Tableau Public.* 

### Save Your First Visualization

#### How to Create Your Profile
- Go back to [Tableau Public's website](https://public.tableau.com/en-us/s/)
- Click on the *SIGN IN* button in the top right corner of the page
- Click *Create one now for free* at the bottom of the pop up box
- Fill in your name, email, and password for your profile
- Verify your account through the email Tableau has just sent you

*TODO Insert profile screenshots here*

#### How to Publish Your Visualizations
- Now that you have an account, go back to your Tableau visualization
- Click on *File*, and then *Save to Tableau Public*
- Enter your account's email and password into the pop up box
- Give your Tableau workbook a name, like *My Very First Visualization*
- As soon as you press save, Tableau will upload your workbook and launch your profile in a web browser.
- There's your visualization! Test it out. Try adjusting the year filter or hovering over each region's line.
- Click *My Profile* to return to your profile. This is where all of your visualizations will be saved during the course.

*TODO Insert publishing screenshots here*


## Getting set up with GitHub and GitHub Pages

GitHub is an invaluable tool for version control, collaboration, and distribution. It also allows users to create free websites that draw directly from the Github *repository* they are associated with. This tutorial will walk you through the process of setting up a GitHub repository, making changes to your Github folder, and creating your first GitHub page. By the end of this tutorial you will:

* Have a GitHub Account
* Interact with GitHub via the Desktop GUI (graphical user interface)
* Be able to utilize GitHub for storing projects
* Have a "Hello World" GitHub page with a blog post structure in place

The example site is here: []

#### Set Up

First, you will set up a GitHub account through the browser. Navigate to [github.com](https://github.com/) and Sign Up for a new account. Log in with your new account.

Now navigate to [desktop.github.com](https://desktop.github.com/) and click on the download button. Follow the prompts on screen until the download has completed and you have installed the program. 

Now navigate to a folder on your computer. In your Documents or [username] are good places do **NOT** set it up in a cloud-based service like Dropbox or GoogleDrive). Make a new folder for this class. I'm going to call mine "dataviz_sample", you can call it anything (as long as there are no spaces - use an underscore), but you will be using it for the entire semester. Your website will be: https://github.com/[USERNAME]/[FOLDER]/. So mine is https://github.com/michellejm/dataviz_sample/.


Now, open a text editor ([Sublime](https://www.sublimetext.com/), Atom, and BBEdit are good choices Notepad and TextEdit are fine. MSWord, OpenWord, and Google Docs are not text editors). If you do not have a text editor, we recommend Sublime. You will need a text editor throughout the course.

Open a new document and type a couple words into it (I usually write "Hello World"). Name it 'index.md' and save it into your new folder. This will be your first webpage! The way websites work is that they always read from the index file first. 'md' stands for 'Markdown'. We will be using [Github-flavored markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

Now that you have all the pieces lined up:
1. A GitHub Username
2. GitHub Desktop installed
3. A folder for your projects
4. A docs folder for your website files
5. An empty document

It is time to push your folder to your online repository.

#### Linking a Repository

Open GitHub Desktop. Log in with your new username and password, and then you will see an empty program box.

Click on the plus sign in the upper left corner

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/git2.png)

Click on the `Add` button.

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/git3.png)

The file navigator should appear. Navigate to the file you just created (for me, that's dataviz_sample) The folder will appear in the panel to the left. Click on the Foldername and then click `Publish`. 

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/git4.png)

Now return to GitHub.com in the browser and you should see a repository with the name of your project. If you don't see it, click on your avatar in the upper right corner, then 'Your Profile' and it should be on that page. 

#### Creating a Webpage

Now click on 'Settings' on the far right corner.

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/git5.png)

Scroll down to 'GitHub Pages'

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/git6.png)

Select 'Master branch' and then 'Save' and then 'Themes'

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/git7.png)

Pick your theme (you can change this later). You will be taken back to the repository where you will see a `_config.yml` file. This file controls the styling of your site and tells the browser how to render it.

Now go back to the **Settings** tab and scroll down to the Pages options, and you will see a link to your new website. Congratulations! Your site is live!

Click the back button to go back to the **Code** tab (you may want to keep both the website and the repository open in different tabs)

We probably want to make some edits to this site. You can use the editor in the browser or the text editor on your computer to make these changes. I am going to use the editor in the browser. First, I am being prompted to make a `README.md` file. It is good practice to always include a readme to tell people what your repository is about. We will create one by clicking on the `Create README.md` button. Add some plain text here, maybe saying this is a class website. 

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/git9.png)

Scroll to the bottom and Commit your changes.

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/git10.png)

You will be redirected to the list of files. Click on `Create New File`. Name this file **blogpost1.md**, and enter some dummy text such as "Hello World". You can preview what it looks like on the `Preview` Tab under the file name. 

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/git11.png)

When you are satisfied, scroll to the bottom of the page, and `Commit` your changes. 

Now, we want to link this page from our landing page. 

Return to our root directory by clicking on the name of the repository at the top of the page. Open your `index.md file``, and select the `Edit` button

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/git8.png)

Add a title to your file using one hash tag (this makes Header size 1-the biggest):

`# My first blog post`

Add a subheader with either 2, 3, or 4 hashtags (depending on what size you want it). And add a link to blogpost1.md by enclosing the linked words in square brackets, and the location of the file in parentheses after it (./ tells this file to look for a file in the same level of the document tree - NOTE the forward slash! A backslash will find the *file* - not the page). 

`### [311 Visualization](./blogpost1.md)` 

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/git12.png)

Check how it looks in the preview. If you are satisfied, commit your changes and go check out your website! Congratulations! You have a landing page and your first blog post set up. You will follow the same steps for the second blogpost, final project, and white paper, making a new document for each one, and linking it from your landing page. 

#### Syncing Github Pull and Push

We have made a lot of changes to our Github files, but we have only done it remotely - not on our local computer. We need to sync these. Return to the GitHub **Desktop**

There may be green or red highlighting - maybe not. Click on `Sync` then make a commit message (I wrote "update"), and select `Commit to master`. Go and check the folder on your computer - all of your new files should be there.

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/git13.png)

Be sure to do this periodically to keep everything synced.

#### Embedding Tableau Public

Once you have posted your visualization to Tableau Public, you can embed it into your pages. Here, I am going to embed a visualization from my Tableau Public account into my Blog Post 1 page. We will need to make an `_includes` folder in the root of our GitHub Repository. 

Select `Create New File`

Type: `_includes/plot1.html`  (you must type `_includes` exactly, the name of the plot is irrelevant, and you will make many more).

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/git15.png)

This will make a new Folder **and** a new file at the same time. You might have noticed that the ending of this file is `.html` rather than `.md`. 

The interactive features of your chart will only work in an html file because they are calling on *another* programming language: Javascript. Since our focus here is data visualization (not web development - though there is a large space where those overlap), we aren't going to get into the details of this too much. Suffice it to say that GitHub pages allows a low barrier way to create a website by transforming Markdown (which looks a lot like plain language) into HTML and CSS, but Tableau uses Javascript. Those three languages together provide the structure, styling, and interaction (respectively) that you see on the web. To get around this constraint, we are going to embed our Tableau Public chart as a function within our markdown file. 

Now open the `plot1.html` file for editing. 

Type the following code (not the CODE HERE part)

```
<html>
	<body>

	[CODE HERE]

	</body>
</html>
```


![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/git17.png)


Now, navigate to your Tableau Public repository [or mine for now](https://public.tableau.com/views/shootings_1/Sheet1?:embed=y&:display_count=yes&publish=yes)). Make any last edits to the visualization with `Edit Details` at the top. Then click on the `Share` icon at the bottom of the page (it's within the visualization frame)

![tableau](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/tableau1.png)

Copy the `Embed` code (on the top).

![tableau](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/tableau2.png)

Return to the `plot1.html` file you were just editing and paste this link between the `<body>` tags. 

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/git14.png)

Commit your changes. Now we are going to go back to our blogpost1.md file and make a link to this html file. Open the `blogpost1.md` file for editing.

Type `{% include plot1.html %}` where you would like your plot to appear. This tells our page that it should go and look for the *function* plot1.html in the `_includes` folder. The curly braces, percentage signs, and spaces are all essential. NOTE! Preview will not work for this because you are referencing another file.

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/git16.png)


Commit your changes and reload the page. The visualization should appear NOTE! This may take some time - sometimes the rendering goes slowly. If there is a problem, you will get a build error in your email almost immediately. 

We have now built the structure for your site. You will make more blog posts, more plots, and more links. In general, the structure looks like this:

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/structure.png)


Now go back to the GitHub Desktop and sync your folders. Click the Sync button, wait for the changes to appear, write a commit message, and commit your changes (there may be no changes to commit. If so, just click the `Sync` button). 

#### Change headers and other meta data

You can change the headers, logos, etc. in the `yaml` file. Go back to your gitHub repository and open the `_config.yml` file for editing. 

Right now, it just has the default settings (depending on your Theme, there may be more or less information here)

Don't change the name of your theme. You can add (or change) the following attributes:

```title:
description: 
layout: (usually this will be `post`)
logo: (must be located in an `img` folder!)
```
[and more](https://jekyllrb.com/docs/frontmatter/)

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/git19.png)

Congratulations!! You have set up a github account, created a page using Markdown, and embedded an interactive graphic into a webpage. You will use this structure to submit all of your projects. 

You will need to write your posts in Markdown. Here's a [complete guide](https://guides.github.com/features/mastering-markdown/) and a [cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

On your own, **put a link back to the HomePage (index.md)** at the top of your blog posts.

As it stands, our site obviously needs a lot of work since just have dummy content, and we haven't done much in the way of formatting, but the basic structure is there. You can change your site as you go along. 


If you are comfortable with this workflow, you can customize your site as much as you would like using [Jekyll](https://jekyllrb.com/docs/github-pages/). If you are already (even a little bit) familiar with web development, feel free to use bootstrap or any other tool to build [your site](https://pages.github.com/).

______________________________________________________________________________________________________________

Tutorial written by [Michelle McSweeney](www.michelleamcsweeney.com), for *Introduction to Data Visualization*, a course in the M.A. in Digital Humanities at the Graduate Center at CUNY. More information about the program is available [here](https://www.gc.cuny.edu/Page-Elements/Academics-Research-Centers-Initiatives/Masters-Programs/Digital-Humanities).



 
