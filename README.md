# README

The following are a set of instructions describing how the resume was set up and hosted on Github Pages for anyone who wishes to use a markup language and host documents online. These instruction sets are focused on using Pelican as the static site generator, Github as the forge and Markdown as the language of choice. Keep in mind these are not the only tools available to perform this task.

## Pre-requisites
Few required software to follow along with the instructions:
* #### Python
  * To install the latest version go to the [Python website](https://www.python.org/downloads/) and click "Download Python (version)" and install on the system.   
  * Additionally, it can be installed on Windows by going to the Windows Store and searching for Python.(Need to have an account logged into the store) 
* #### Pelican - Static site Generator
  * Install Pelican by going to the command prompt and typing ``python -m pip install "pelican[markdown]"``
* Install ghp-import: ``python -m pip install ghp-import``
* Install Git by going [here.](https://git-scm.com/)
* Create an account on [GitHub](https://github.com/)

## Create content using Markdown
* The first step in creating a content file for Pelican is to have the following three fields <br> Title: <br> Date: yyyy-mm-dd hh:mm <br> Author:
* As per general principle of style by Etter, the headings and the formatting is consistent
* As per general principle to build a website by Etter, this resume is hosted on a website generated by Github Pages so any new changes will be viewed by the users.
* As per Etter, it is better to use a lightweight markup like Markdown as this is easier to make changes to by the general audience. This is one reason Markdown is the preferred choice
* Etter advises to use distributed version control, this is the reason we are using Github
* For headings in Markdown we use the # symbol. The number of # will determine how big the heading will be. For instance, # is the biggest heading and was used for the name, ## for any following headings and #### to show the content in bold.
* To create a list, we use a '*' before the line and a bullet is added.
* \<br> is frequently used to start anything after the command on a new line
* \&nbsp; moves to the content right by one tab space

## How to sync to Github and Github Pages
*  Log into your Github account and create a new repository. [How to create a git repository?](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-new-repository)
*  Open command prompt
*  Enter ``pelican-quickstart``
*  This will initialize Pelican and followed by a series of questions in regard to the new site tobe generated
*  A few questions are as follows:
   * Where do you want to create the new web site? If you want to create in the current directory, hit enter or else enter the directory path.
   * Do you want to specify a URL prefix? 
     * Since we want our site to be hosted on Github, the answer to this questions is 'Y'
     * In the following prompt, enter: ``https://username.github.io/example`` where username is your Github username and example can be changed with the repository you want this site to sync with.<br>
 _NOTE: Keep in mind if you hit enter for any of the questions the default selection will be the letter that is uppercase. For instance, (y,N) would have the default answer to be No._
* After generating the static site, we need to sync the folder with the git repository
* In command prompt, got to the folder where the files for static site are present.
* Type ``git init``, this command initializes an empty git repository in the current folder.
* Followed by ``git add .``
  * The '.' ensures all the files and folders in the current directory are added
* Commit the files using ``git commit -am "Any comment"``
* Now to sync the files with the git repository enter, ``git remote add origin https://github.com/Username/(Repository Name).git``
* Ensure you are on the main branch, ``git branch -M main``
* Once ready, push these files to the git repository, `` git push -u origin main``
* Enter the following commands to generate the site and deploy to Github pages <br>
```
pelican content -s publishconf.py
ghp-import output -b gh-pages
git push origin gh-pages 
```
*  Run the above commands after any local updates to the content folder.
*  To open the website simply type in https://username.github.io/repository_name/ in the web browser.

## Additional Resources

For detailed information of the concepts mentioned here, you can use the following websites
1. https://git-scm.com/docs/git - provides most up to date information on how to use the git commands
2. https://www.markdownguide.org/basic-syntax/ - guide to the most commonly used Markdown commands
3. https://antonellocalamea.medium.com/step-by-step-guide-to-setup-a-web-site-using-pelican-and-gitpages-5de976ae44cb - detailed guide on how to get set up with pelican
4. https://www.freecodecamp.org/news/command-line-commands-cli-tutorial/ - A selection of command-line commands to help you navigate and get familiar with the system.
5. https://about.gitlab.com/blog/2022/04/18/comparing-static-site-generators/ - information on static site generators
6. https://www.computerweekly.com/blog/Open-Source-Insider/What-is-a-software-forge - brief description of a forge

## FAQ

Q. Why do I need Github Pages when I can generate and view a static site using Pelican?<br>
A. Pelican only hosts the site locally while Github Pages hosts it on the internet for others to see. 

Q. Can I use any other markup language?<br>
A. Yes, you can use any markup language. Markdown is used here as an example while also keeping in mind it takes less time to learn Markdown compared to some other languages but a more complex language will have more functionalities that Markdown might be missing.

Q. Why am I unable to see some of the files on Github even after running ghp-import and push commands?<br>
A. The three commands that include pelican content, ghp-import and git push are used to push the html files to the gh-pages branch. To push the files online, make sure to use git add, commit and then push, this will be needed if there are any changes made to the files or folder structure.

## Credits

This readme was written by Arshinder Singh Sidhu with contributions from Lucas Berzuk and Laurel Lassi. Some ideas have been used from Modern Technical Writing by Andrew Etter.