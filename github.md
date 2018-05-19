## Getting set up with GitHub and GitHub Pages

GitHub is an invaluable tool for version control, collaboration, and distribution. It also allows users to create free websites that draw directly from the Github *repository* they are associated with. This tutorial will walk you through the process of setting up a GitHub repository, making changes to your Github folder, and creating your first GitHub page. By the end of this tutorial you will:

* Have a GitHub Account
* Interact with GitHub via the Desktop GUI (graphical user interface)
* Be able to utilize GitHub for storing projects
* Have a "Hello World" GitHub page with a blog post structure in place

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

Pick your theme (you can change this later). You will be taken back to the repository where you will see a `_yaml` file. This file controls the styling of your site and tells the browser how to render it.

Now go back to the **Settings** tab and scroll down to the Pages options, and you will see a link to your new website. Congratulations! Your site is live!

Click the back button to go back to the **Code** tab (you may want to keep both the website and the repository open in different tabs)

We probably want to make some edits to this site. You can use the editor in the browser or the text editor on your computer to make these changes. I am going to use the editor in the browser. First, I am being prompted to make a `README.md` file. It is good practice to always include a readme to tell people what your repository is about. We will create one by clicking on the `Create README.md` button. Add some plain text here, maybe saying this is a class website. 

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/git9.png)

Scroll to the bottom and Commit your changes.

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/git10.png)

You will be redirected to the list of files. Click on `Create New File`. Name this file blogpost1.md, and enter some content. You can preview what it looks like on the `Preview` Tab under the file name. 

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/git11.png)

When you are satisfied, scroll to the bottom of the page, and `Commit` your changes. 

Now, we want to link this page from our landing page. 

Return to our root directory by clicking on the name of the repository at the top of the page. Open your index.md file, and select the `Edit` button

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/git8.png)

Add to your file a header using:

`# Header`

Add a subheader with either 2, 3, or 4 hashtags (depending on what size you want it). And add a link to blogpost1.md by enclosing the linked words in square brackets, and the location of the file in parentheses after it (./ tells this file to look for a file in the same level of the document tree). 

`### [311 Visualization](./blogpost1.md)` 

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/git12.png)

Check how it looks in the preview. If you are satisfied, commit your changes and go check out your website! Congratulations! You have a landing page and your first blog post set up. You will follow the same steps for the second blogpost, final project, and white paper, making a new document for each one, and linking it from your landing page. 

#### Syncing Github Pull and Push

We have made a lot of changes to our Github files, but we have only done it remotely - not on our local computer. We need to sync these. Return to the GitHub **Desktop**

There may be green or red highlighting - maybe not. Click on `Sync` then make a commit message (I wrote "update"), and select `Commit to master`. Go and check the folder on your computer - all of your new files should be there.

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/git13.png)

Be sure to do this periodically to keep everything synced.

#### Embedding Tableau Public

Once you have posted your visualization to Tableau Public, you can embed it into your pages. Here, I am going to embed a visualization from my Tableau Public account into my Blog Post 1 page. 

Go back to Github in the browser. Navigate to your Tableau Public repository [or mine for now](https://public.tableau.com/views/shootings_1/Sheet1?:embed=y&:display_count=yes&publish=yes)). Make any last edits to the visualization with `Edit Details` at the top. Then click on the `Share` icon at the bottom of the page (it's within the visualization frame)

![tableau](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/tableau1.png)

Copy the `Embed` code (on the top).

![tableau](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/tableau2.png)

Return to the GitHub **Website** and your blogpost1.md file. Paste this link where you want the visualization to appear. Select Preview to be sure it looks the way you expect and then commit your changes.  

![git](https://github.com/dataviz-gc/intro-dataviz-summer18/blob/master/img/git14.png)
