## Peer Feedback



For this weeks exercises, you will give each other peer feedback. We will assign each of you to review the submission of one of your classmates and provide you with the according Github URL. Once you have this URL, clone the repo to your local hard drive in the following manner:

1. In RStudio, start a new project
2. Choose: File > New Project > Version Control > Git.
3. In the repository URL, paste the URL from your classmate

This will create a clone of that project on your local machine and open it in RStudio. You can now run the script of your classmate and think on how you would improve his or her solution. To provide your classmate with feedback to specific parts of the code, we recommend the following approach.

1. Open your classmates repository on github.com
2. Find and open the R / RMarkdown script containing the code you want to provide feedback on
3. Highlight the lines you want to reference by clicking on the respective line numbers (you can select multiple lines by selecting the first line, holding the shift key and then selecting the last line)
4. Click on the three dots situatied to the left of the first line
5. Choose *Reference in new issue*. This will create a new issue with a link referencing the specific lines.
6. Add your comment

"Issues" is a great way to provide feedback on a codebase. Your classmate can now review your comment, provide an answer and "close" the issue once it is resolved. 


![](https://github.blog/wp-content/uploads/2017/08/29093044-6477ba12-7c56-11e7-9bd2-e6db926d70be.gif?resize=1360%2C600)

**RStudio Addin**

Switching between RStudio and Github.com can be inefficient and cumbersome. We have therefore created an RStudio Addin to allow you to write issues directly from within RStudio. To use this addin, you will need to install it first with the following instruction:
  
1. Install `devtools` (`install.packages("devtools")`)
2. Install `inlineComments` from Github ([ComputationalMovementAnalysis/inlineComments](https://github.com/ComputationalMovementAnalysis/inlineComments), via `devtools::install_github("ComputationalMovementAnalysis/inlineComments")`)
4. Restart RStudio
5. Click on *tools > Modify keyboard shortcuts* and add a shortcut for the command *Insert inline comment* (e.g. `Ctrl + Shift + k`)

Now for each comment, you can highlight the lines you wish to comment and use the keyboard shortcut you assigned in the last step (e.g. `Ctrl + Shift + k`). This should open a window where you can add your comment. If you hit *Create issue*, an issue will be added to your fellow student's repo and a message will show you a link to the new issue.

