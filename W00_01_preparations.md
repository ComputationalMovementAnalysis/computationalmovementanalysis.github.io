# Preparation {#w0-preparation}

In this course we will be using `R`, RStudio and Git. We ask you to install and/or update these programms *before* the start of the course, so that we do not loose time once the course starts. We cover the version number we expect you to have and provide some tips on how you should change your RStudio settings. 







## Check you version of `R`

Check your Version of `R` by opening RStudio and typing the following command into the console. 


```r
R.version.string
## [1] "R version 4.1.3 (2022-03-10)"
```

This returns the version number of your R installation, whereas the first digit (`4`) indicates the number of the *major release*, the second digit  (`1`) indicates the *minor release* and the last digit (`3`) refers to the *patch release*. As a general rule of thumb, you will want to update R if you

- don't have the current *major* version or
- are lagging two (or more) versions behind the current *minor release*

In the time of writing (März, 2022), the current `R` Version is 4.1.3 (released on 2022-03-10 08:05:38, see [cran.r-project.org](https://cran.r-project.org/)). Your installation should therefore not be older than 4.0.0. If it is, make sure that you have updated R until next week (doing it now will probably take too long). Check [these instructions on how to update R](https://www.linkedin.com/pulse/3-methods-update-r-rstudio-windows-mac-woratana-ngarmtrakulchol/)


## Check your version of RStudio

RStudio is the Graphical User Interface (GUI) we use in our course to interact with R. RStudio should not be too old either and we recommend updating if you don't have the latest version: check if this is the case by clicking on *help > check for updates*. If you need to update RStudio, don't update now but have a newer version of RStudio installed before next week. 


## Install the necessary packages

If you haven't already, install the packages `tidyverse`, `sf` and `terra`(using `install.packages()`). 


```r
install.packages("rmarkdown")
install.packages("dplyr")
install.packages("ggplot2")
install.packages("readr")
install.packages("tidyr")
install.packages("sf")
install.packages("terra")
```


## Install Git{#install-git}

Next, install Git. There are different Git installers to choose from, we recommend the following:

<!-- If you are not sure whether you already have Git installed or not, you can verify this by typing `git --version` in the terminal. If this command returns a version number you have Git installed already and might only need to update it. If this command returns `git: command not found` (or something similar), you will need to install Git first. -->


- **Windows**: 
  - We recommend installing [Git for Windows](https://gitforwindows.org/), also known as `msysgit` or “Git Bash". 
  - When asked about “Adjusting your PATH environment”, select “Git from the command line and also from 3rd-party software”
  - RStudio prefers Git to be installed in `C:/Program Files/Git`, we recommend following this convention
  - Otherwise, we believe it is good to accept the defaults
- **macOS**:  
  - We recommend you install the Xcode command line tools (not all of Xcode), which includes Git
  - Go to the shell and enter `xcode-select --install` to install developer command line tools
- **Linux**: 
  - On Ubuntu or Debian Linux: `sudo apt-get install git`
  - On Fedora or RedHat Linux: `sudo yum install git`
  

Much of this chapter was taken from @bryan2021. If you want to dive deeper into using Git, we highly recommend this book. For an *even* deeper dive into Git, read @chacon2014. Both books are available free and open source on [happygitwithr.com](https://happygitwithr.com/) and [git-scm.com/book](https://git-scm.com/book/), respectively.

## Configure RStudio{#configure-rstudio}

Now we will set some RStudio Global options. But first, **close all instances of RStudio and restart it (!!!)**. Then go to Tools > Global options. 

- **R General**
  - Deactivate the option "Restore .RData into workspace at startup"[^restore]
  - Set "Save workspace to .RData on exit " to "Never"[^saveworkspace]
- **Git / SVN**
  - Activate the option "Enable version control interface for RStudio projects"
  - If the Field "Git executable:" shows `(Not Found)`, browse to your git installation (previous step). This path should look something like this:
    - Windows: `C:/Program Files/Git/bin/git.exe` (**not** `C:/Program Files/Git/cmd/git.exe` or `some-path/git-bash.exe`)
    - Linux / macOS: `/usr/bin/git`
- **Terminal**
  - Set option "New terminals open with" to "Git Bash" 
  
Click on "Ok" to apply the change and close the options menu.

[^restore]: We recommend that you start each RStudio session with a blank slate, as recommended by @wickham2017 see [here](https://r4ds.had.co.nz/workflow-projects.html)
[^saveworkspace]: If we don't restore the workspace at startup, there is no need to save it on exit.



## Introduce yourself to Git{#introduce-yourself-git}

Now it is time to introduce yourself to git. For this, we need to use the shell terminal, which is why we are going to spend a few word on the shell first. 

The shell is a program on your computer whose job is to run other programs. It looks very much like the `R`-console (in the bottom left of RStudio) that you are already know: You have a place to input text which is transferred to (and interpreted by) the computer when you press "enter". RStudio has a shell terminal right next to the `R`-console (tab `Terminal`).

Every Windows comes with two different shell installations: "Command prompt" and "PowerShell". After installing Git we now have a third option, "Git Bash". The shell terminal in RStudio uses "Command prompt" per default, in [the last step](#configure-rstudio) we just switched the shell to "Git Bash".

Now use the terminal in RStudio to introduce yourself:

```
git config --global user.name "Maria Nusslinger"
git config --global user.email "nussmar@email.com"
```

Of course, replace the name and address with your credentials. Use the email address that you will use to create your Git*hub* account (which we will do next week).

**Note to users who already have a Github account:**

If you already have a Github account and don't want to associate the work you do in this course with said account, we recommend the following approach:

1. Create a new Github account with a different mailaddress (e.g. your student mail address)
2. Override your `user.name` and `user.email` on a per project basis (by omitting the `--global` flag)

Please feel free to contact us if you have questions about this.
