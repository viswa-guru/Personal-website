# Making websites with RMarkdown and GitHub

The example website for this course is located at https://eeb504.github.io/rmarkdown-website-examples/index.html.

## Git usage reminders

Broadly speaking, there are two classes of `git` commands that we have introduced in this short course. The first deals with actions (staging, committing, and pushing to a remote server--e.g. GitHub). The second set is diagnostic (What is going on in this repository--what is its status? What differences have I made for files that are tracked? What differences are staged?).

### Setting up a repository using Git and GitHub

When you have a new project (such as a new manuscript, thesis chapter, research project, lab protocol, etc.), and seek to set up a new Git repository for this project (which will encompass a parent folder, potential sub-folders, and files), we recommend the following steps:

* Go online to GitHub.com and click on the `+` sign in the upper right and select `New Repository` (not `Import Repository`, `New Gist`, or `New Organization`). ![NewRepo](docs/images/CreateNewRepo.png?raw=true?raw=true)
* Give your repository an informative name and a brief description. This description will be the initial `README.md` file (and this `README` file is what people see when they navigate to your repository, assuming that it is public). Check the box for `Initialize this repository with a README` and make selections for the drop-down menus in `Add .gitignore` (you can search for popular languages like R, or python) as well as `Add a license` (the `(i)` icon next to the `Add a license` drop-down menu provides information on different options, though for academics, `GNU General Public License v 3.0` and `MIT License` are generally popular).
* Clone the repository from GitHub to your local machine. The steps differ based on your client for Git.
    + If you use terminal to execute local Git commands, navigate to the `Clone or download` drop-down menu in your GitHub repository and copy the `Clone with HTTPS` address (e.g. `https://github.com/EEB504/rmarkdown-website-examples.git`).
        * Subsequently, in terminal, navigate to the directory where you would like the repository to be located (e.g. `/Users/MYNAME/Documents` or `/Users/MYNAME/Dropbox`) using the command `$ cd /Users/MYNAME/FOLDER`
        * Use the command `$ git clone https://github.com/YourAccount/RepositoryName.git`. This will create a new folder in this directory with the name of the repository (e.g. `/Users/Char/Documents/MyRepository`).
    + If you use a graphical interface like GitHub Desktop, GitKraken, or SourceTree, use the menu to clone the repository. As long as your GitHub account as synced with this desktop client, it should be pre-populated in their drop-down menu.
* Once the repository is on your local machine, begin creating files for analysis and writing up your projects! (Or move the files over and begin tracking them.)

*Action Steps*

### New files or files that are not yet tracked

* `git add`: begins tracking a new file and stages any information (e.g. text) contained in that file.
    + Until you tell git to track a file with `git add`, it will **not** record any changes to this file. Git ignores files until you use `git add Filname.Extension`. After that file is added and committed, git will then track any changes made to this file through time.
* `git commit`: this command formally saves the changes introduced in the previous `git add` command to the local repository.
    + If you are using a terminal shell, I advocate for using `git commit -m "INFORMATIVE MESSAGE"` as the `-m` flag lets you append a short commit message inline (without having to use Nano/vi/vim to write a message, save it, and exit).
* `git push origin master`: this command publishes (or pushes) the changes performed in the last commit to your remote repository (most often, a GitHub repository).

### Files already tracked by Git

* `git add`: stages any *changes* made to files that are already tracked.
* `git commit`: this command formally saves the changes introduced in the previous `git add` command to the local repository.
    + If you are using a terminal shell, I advocate for using `git commit -m "INFORMATIVE MESSAGE"` as the `-m` flag lets you append a short commit message inline (without having to use Nano/vi/vim to write a message, save it, and exit).
* `git push origin master`: this command publishes (or pushes) the changes performed in the last commit to your remote repository (most often, a GitHub repository).

*Diagnostic steps*

Using terminal as your Git client:

* `git status`: What is the state of my repository?
    + `Changes not staged for commit:...` What files have changed since the last checkpoint?
    + `Untracked files:` Files that are not yet tracked by Git. You may well have files that you never want Git to track (such as `.jpeg` or even some scratch script files) but you may want to avoid adding their extensions into the `.gitignore` file because sometimes, some of those types of files may have meaningful changes while others may not. For me, this is typical for serialized `.rda` files (R data object files); sometimes I want to track these; other times I don't. Note that the default `.gitignore` populated by GitHub for `R` includes `.RData` as a file type to ignore.
        * If the last checkpoint was the initial `git clone` command, you would see that any new files or files moved into this repository are listed as `Untracked files` unless they hae an extension that is excluded by the `.gitignore` file (such as `.Rhistory` for a `R` based `.gitignore`).
    + Note that if you use a graphical client like GitHub Desktop or GitKraken, the view pane effectively shows you the `git status` -- what files have changed, etc.
    + In terminal, you would navigate to your repository (`$ cd /path/to/my/repository`) and then execute `$ git status`.
*  `git diff`: What are the specific changes that have happened since the last checkpoint? (Each checkpoint for the entire repository is associated with a specific `git commit`)
    + In terminal, `git diff --cached` is how you see changes that are staged (`git add`) whereas `git diff` shows you changes to all tracked files that are not yet staged.
    + In a graphical client, whenever you click on a file that has changed, it should show the changes that have happened.

FMI:

* [Happy Git with R](http://happygitwithr.com/new-github-first.html)
    + Chapter [16 (New Project, GitHub First)](http://happygitwithr.com/new-github-first.html)
    + Chapter [17 (Existing Project, GitHub First)](http://happygitwithr.com/existing-github-first.html).
    + We do **not** recommend the workflow in Chapter 18 (Existing project, GitHub last); as Jenny Bryan notes, "This is less desirable for a novice because there are more opportunities to get confused and make a mistake."
    + This is arguably one of the best resources for learning how to use Git and though it is written for R users, many of the suggestions would also port to python and other languages
* [Red Badger](https://blog.red-badger.com/blog/2016/11/29/gitgithub-in-plain-english)
* [Gousset learning Git on Windows](http://mickeygousset.com/getting-started-with-git-for-windows/)
* [Git Tower](https://www.git-tower.com/learn/git/commands/)

## Instructions

### Part 1: Forking and renaming the repository in GitHub
1. Navigate to https://github.com/EEB504/rmarkdown-website-examples
    * Note that steps 1-4 are **all** performed online on GitHub
2. Fork this repository (`rmarkdown-website-examples`)
    * ![ForkIcon](docs/images/forkIcon.png?raw=true)
3. After forking, rename this repository
    * For example, you may want to name the repository `YOURNAME.github.io`; or `YOURNAME`; or `YOURNAME-website`, etc. ![Renaming](docs/images/renamingRepo.png?raw=true)
4. Obtain the Clone link ![CloneLink](docs/images/gitCloneLink.png?raw=true)

### Part 2: Cloning the repository from GitHub to your local machine

5. Navigate back to your local machine
6. In the shell (terminal) or in a Git client such as GitHub Desktop, SourceTree, GitKraken, or any other [client](http://happygitwithr.com/git-client.html), perform the operation:
    * In terminal:
        * Navigate to the desired parent directory where you would like this repository to live on your local machine. For me, this is often either `/Users/Char/Documents` or `/Users/Char/Google Drive/`. To perform this command in the shell, you would do something along the lines of `$ cd ~/Documents` or `$ cd ~/GoogleDrive`
        * `$ git clone https://github.com/YOURUSERNAME/REPONAME`
        * For instance, for the EEB504/rmarkdown-website-examples repository, this would look like `$ git clone https://github.com/EEB504/rmarkdown-website-examples.git`
    * In a local Git client, note that the commands will resemble these from GitHub desktop:
        * Either go to `File -> Clone Repository` or use the `+` icon and select `clone` ![CloneIcon](docs/images/GitHubDeskClone.png?raw=true)
        * Subsequently, select where you want this repository to be housed on your local machine ![DirectorySelection](docs/images/GitHubDeskDir.png?raw=true)
        * You should then see the repository on your local machine: ![LocalRepo](docs/images/GitHubDeskRepo.png?raw=true)

### Part 3: Building an initial version of your own website

7. Using either `Finder` (Mac OS) or `File Explorer` (Windows), navigate to the directory where the repository is located. Navigate to the folder called `docs`.

#### Part 3, Version 1: Using RStudio

If you only have the R Console installed, these files will open but your workflow will need to be different. See Part 3, Version 2.

8. Note that the `.Rproj` file will let you open a `R Project` in `RStudio` where you can edit the website contents.
    * **Before** you open the `.Rproj` file, you may want to rename it so that its name matches the name of your repository. For instance, here is an example where I am re-naming `rmarkdown-website-examples.Rproj` to `test-website.Rproj` in `Finder` on my Mac. ![renameRproj](docs/images/RprojRenaming.png?raw=true)
    * It isn't necessary that you do this, but it may be useful for future reference.
9. Open (double click) the file `FILENAME.Rproj` (for example, on my machine, it has been renamed `test-website.Rproj`); this will open RStudio (if it is installed on your machine).
    * If you renamed the `.Rproj` file, perform these next steps:
    * In RStudio, you should now see a small, vertical `Git` icon. Click on this as you will need to git stage and commit the fact that you renamed the `.Rproj` file. ![GitIconRStudio](docs/images/GitIconRStudio.png?raw=true)
    * Perform the equivalent of the `git add` and `git rm` (remove) command in the Git console in RStudio by clicking on the two boxes on the left-hand side. ![GitAddRStudio](docs/images/RprojRenamingGitStaging.png?raw=true); this will subsequently produce this image: ![GitRename](docs/images/RprojRenamedRStudioGit.png?raw=true)
    * Write an informative `git commit` message ![GitCommit](docs/images/RprojRenamedCommitMsg.png?raw=true)
    * This will open a shell that displays what is happening when you click on the `Commit` button ![RGitCommitShell](docs/images/RStudioCommitMessage.png?raw=true)
10. Begin website development!
11. Make changes to `about.Rmd` to change your `About Me` page.
    * For example, I added the line `Test, test` to the bottom of the `about.Rmd` file.
12. Before we can see any of these changes reflected online, we need to go into the R console (in my version of RStudio, this is in the upper right-hand corner) and use the command `rmarkdown::render_site()` to generate updated `HTML` pages. (This calls the command `render_site()` from the `rmarkdown` package).
    * Note that you would need to have `rmarkdown` installed as a package.
    * If you do not have this package on your local machine, perform this command in the R console: `install.packages("rmarkdown")`. Once you have a package installed, you do not need to re-install it (unless you update your version of `R`). ![rmarkdownrender](docs/images/rmarkdownrendersite.png?raw=true)
13. Perform the `git add` (staging; this is done by clicking the box for each file under the left-hand `Staged` column) and `git commit` commands in the `Git` console in RStudio. ![GitCommit](docs/images/AboutCommitRStudio.png?raw=true)
14. Now that you have completed a set of changes for your website, select `git push` in the `RStudio Git` console. ![GitPushRStudio](docs/images/PushRStudio.png?raw=true)

##### Part 3, Version 2, Using a text editor and an R script

8. Begin developing your website!
9. Open and edit `about.Rmd` in the text editor of your choice (this may be Atom, Notepad ++, or good old TextEdit or Notepad)
10. Build your website in either the R Console or in a terminal shell.
11. In R Console:
    * Use the command `setwd()` to change the working directory to the correct
    * Enter and run the command `rmarkdown::render_site()`
12. In a terminal shell: run the command `Rscript build_site.R`
13. Use Git in GitHub Desktop, GitKraken, or in a terminal shell to `git add` and `git commit` your changes.
14. In a Git client (GitHub Desktop, GitKraken, SourceTree, etc.):
    * Navigate to your repository in the file menu.
    * Click on button to stage `docs/about.html` and `docs/about.Rmd`
    * Write an informative commit message (e.g. `Added test, test to About Me`) and commit.
15. In the shell:
    * Navigate to the folder where the repository is housed locally
    * Perform `$ git add docs/about.html`; `$ git add docs/about.Rmd`
    * Perform `$ git commit -m "INFORMATIVE MESSAGE"` (e.g. "Added test, test to About Me")

### Part 4: Telling GitHub to host your website

1. In your GitHub account, go to the repository associated with your website. For instance, this may look like `https://github.com/EEB504/rmarkdown-website-examples` (for you, this will look like: `https://github.com/YOURNAME/WebsiteRepoName`)
2. Navigate to `Settings` ![GitHubSettings](docs/images/GitHubSettingsMenu.png?raw=true)
3. Scroll down to `GitHub Pages`. Initially, it will probably state that `GitHub Pages is currently disabled. Select a source below to enable GitHub Pages for this repository.`
    * ![NoPages](docs/images/GitHubNoPage.png?raw=true)
4. Click on the drop-down menu initially called `None` and select `master branch /docs folder` to have the website deployed!

### Part 5: Further improvements to your website

1. You will definitely want to change the website name to your name and probably add on more tabs! To change the website name and home page (`index.Rmd` and `index.html`) edit:
    * `_site.yml`
    * `index.Rmd`
    * Perform the `git add`, `git commit`, and `git push` commands as before.
2. To add more tabs: see [Nick Strayer and Lucy D'Agostino McGown's tutorial](http://nickstrayer.me/RMarkdown_Sites_tutorial/). For adding more content to your website and manipulating the appearance, see the sections following `Show the world who you are.`
    * Note that their command for `touch style.css` is not necessary; you can directly edit the `style.css` file in your `docs` folder.
    * Moreover, you add a new tab to your website by changing (1) `_site.yml` to include another tab (`- text: "New Tab" \cr href: NewTab.html` where `\cr` indicates that `- text:...` and `href:...` should be separated by a newline (enter/carriage return)) and (2) creating another Rmarkdown file (in this case, you would want to name it `NewTab.Rmd`).
        + **Note**: Whenever you seek to make a new tab, know that the `FILENAME.html` link in the `href` line in the `_site.yml` **must** be the same name as `FILENAME.Rmd`. This is because `rmarkdown::render_site()` includes an operation called "knitting" where it converts R Markdown (relatively easy to write) into HTML (relatively painful to write). When the R Markdown file (e.g. `Filename.Rmd` or `NewTab.Rmd` or `about.Rmd`) is knit to HTML, the new HTML file will have the same base filename (so `Filename.html`, `NewTab.html`, `about.html`).
        + For this reason, it is best if your filenames for the `.Rmd` files do not contain spaces (avoid a name like `My Special Tab.Rmd`) or weird special characters (avoid a file name like `I\\love\birds***Wha&&&&.Rmd`). If you do want separation between individual worlds, camel case (e.g. `camelCase.Rmd`, `mySpecialTab.Rmd`) is a good option as are underscores (e.g. `my_Special_Tab.Rmd`, `about_me.Rmd`). You can always combine camel case and underscores (e.g. `Website_AboutMe.Rmd`).
3. If you don't like the default theme or any of the [Jekyll Themes](https://pages.github.com/themes/) ([FMI](https://help.github.com/articles/about-jekyll-themes-on-github/)), open `_config.yml` and delete the line `theme: jekyll-theme-slate` and perform `git add`, `git commit`, and `git push` as usual.
4. The [RStudio RMarkdown Websites](https://rmarkdown.rstudio.com/rmarkdown_websites.htm) site has more information on the tools introduced here. For more information on `RMarkdown` syntax, please see [RMarkdown Overview](https://rmarkdown.rstudio.com/authoring_basics.html) or the [Cheet Sheat](https://www.rstudio.com/wp-content/uploads/2015/02/rmarkdown-cheatsheet.pdf).
