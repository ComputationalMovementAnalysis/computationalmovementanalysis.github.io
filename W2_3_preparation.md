## Preparation {#w2-preparation}

This week, we are going to further leverage Git by connecting it to an online repository. Git on it's own can be useful, but to use all of the advantages its best to combine it with an hosted service like Github.

### Step 1: Create a Github account

**Typically, you do this once (in a lifetime)**

Last week, you worked with git on your local machine, with no way of synchronising your changes with a cloud server. This week you will use Github to sync your changes. To do this, create a Github account on [github.com](https://github.com/) (it's free of course). Use the email address that you [configured in git last week](#introduce-yourself-git). If you are not sure which mail you used, type `git config user.email` in the shell terminal. 

You don't have to use the same username on Github and in Git. When choosing a username on Github, consider the following advice: 

- incorporating your actual name is nice, people like to know who they are dealing with
- choose a name that you are comfortable revealing it to a future boss
- shorter is better than longer
- make it timeless (e.g. don't incorporate your university's name)



### Step 2: Authenticate Git to work with Github

**Typically, you do this once (per computer)**

If we want to push changes from our local repository to your Github cloud repository, Github must verify your credentials. Other software might just ask for your username and password, it's a little different with Git. Basically there are two ways to connect with your remote repo (`ssh` and `https`), we will use `https` in this course. 


First, create a personal access token (PAT) on Github

- Login into [github.com](https://github.com/), click on your user profile (top right) and click on "Settings" 
- Choose *Developer settings > Personal access tokens > Generate new token*
- Add a descriptive note (e.g. `https access from my personal laptop`)
- Select scope "repo"
- Click on "Generate token"
- Copy your new personal access token (in the green box)
  - You won’t be able to see this token again
  - If you loose it, you can simply create a new one
  - If you want to store it, you neeed to treat this Personal access tokens (PAT) like a password. Only store it in a secure place (like a password management app) and *never publish this PAT publicly*


Then, store your PAT in you local Git

- In R, install the `gitcreds` package (`install.packages("gitcreds")`)
- Load this library (`library(gitcreds)`)
- Call the function `gitcreds_set()`
- Respond to the prompt with your PAT from the last step
- Check that you have stored a credential with `gitcreds_get()`
  
  
### Step 3: Create a Git**hub** repo {#create-github-repo}

**Typically, you do this once per project**

Now you can create a repository on Github that you can afterwards connect to your RStudio project from this week (which you will create in the next step). To do this, go to [github.com](https://github.com) and click on the plus sign in the top right corner, then fill in the following information:





- Repository name: Give a meaningful name, e.g.  `cma-week2`
- Description: Give a meaningful description, e.g. `Solving exercise 2 of the course "Computational Movement Analysis"`
- Make the repo public, not private
- Choose `Add a README file`

Click on `Create repository`, then on the green button "Code". Select HTTPS (it might already be selected) and then copy the URL by clicking on the clipboard symbol. The URL should look something list this `https://github.com/YOUR-GITHUB-USERNAME/cma-week2.git`. 



\BeginKnitrBlock{rmdimportant}<div class="rmdimportant">Report this URL back to us via Moodle (under *L2 Data Issues > R Exercises E2 > Exercise 2 (Github URL)*)</div>\EndKnitrBlock{rmdimportant}


### Step 4: Create a new RStudio Project {#w2-project}

**Typically, you do this once per project**

You will now create a new RStudio Project for week 2. Unlike last week, we will create the project in such a way that it is immediately connected to our Git*hub* repo. In RStudio, start a new project. Choose: File > New Project > **Version Control** > Git. 

- In the repository URL, paste the URL you copied in the last step
- Change "Project directory name" to `week2-rexercise` (if you are following [the convention we proposed last week](#folder-structure))
- Change the parent directory (`Create project as a subdirectory of`) to your equivalent of `C:/Users/yourname/semester2/Modul_CMA/week2`

Click on "Create Project". You are now all set and can start with this week's tasks!


**PS**: You just created an RStudio Project which is automatically connected to Github. You can also connect existing local Git repositories (e.g. from week 1) to Github. You have the chance to learn this in [Week 3](#w3-preparation).



<!-- ### Connect your local repo with the remote repository -->

<!-- **Typically, you do this once per project** -->

<!-- In RStudio, open the RStudio project from week 1. Open the terminal[^terminal2] and follow the instructions described in *…or push an existing repository from the command line* in the website you were just forwarded to on Github (under https://github.com/YOUR-GITHUB-USERNAME/cma-week1). These instructions should look something like this: -->


<!-- [^terminal2]: There is a terminal built into RStudio which you can use for this. By default, it is situated in the bottom left corner in the tab named "Terminal" -->


<!-- ``` -->
<!-- git remote add origin https://github.com/YOUR-GITHUB-USERNAME/cma-week2.git -->
<!-- git branch -M main -->
<!-- git push -u origin main -->
<!-- ``` -->

<!-- Type these commands line by line into your terminal. If you want to copy and paste the commands rather than type them: Note that ctrl + V for "pasting" won't work via the keyboard shortcut, you will have to paste by right clicking into the terminal and choosing "paste". Now refresh your repo on Github (https://github.com/YOUR-GITHUB-USERNAME/cma-week1): You should now see the files from week 1 on GitHub. Didn't work? Contact us! -->




