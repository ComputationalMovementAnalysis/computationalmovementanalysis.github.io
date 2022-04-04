## Preparation

### Folder structure for this course {#folder-structure}



By this point, you probably have created a folder for this course somewhere on your computer. In our example, we assume this folder is located here: `C:/Users/yourname/semester1/Modul_CMA` (mentally replace this with your actual path). Before we dive into the exercises, take a minute to think about how you are going to structure your files in this folder. This course will take place over 6 weeks, and in each week you will receive or produce various files. We recommend creating a separate folder for each week, and one folder for the semester project, like so:





```
Course Folder (C:\\Users\\yourname\\semester1\\Modul_CMA)
 ¦--week0                                                
 ¦--week1                                                
 ¦--week2                                                
 ¦--week3                                                
 ¦--week4                                                
 ¦--week5                                                
 ¦--week6                                                
 °--semester_project 
```


For the R-exercises that take place in weeks 0 to 5, we recommend that you create a new RStudio Project each week in subdirectory of the appropriate week. For example, this week your folder structure could look like this: 





```
Folder Week 0 (C:\\Users\\yourname\\semester2\\Modul_CMA\\week1)
 ¦--slides.pdf                                                  
 ¦--my_notes.docx                                               
 ¦--seminar_screenshot.jpg                                      
 °--week0-rexercise                                             
     ¦--week0-rexercise.Rproj                                   
     ¦--wildschwein_BE.csv                                      
     °--my_solution.Rmd   
```


Note: 

- the RStudio Project is located in a subfolder of `` and named `week0-rexercise`.
- `week0-rexercise` is the project's *directory name* and the *project name*
- we realize that that the week number is redundant, there is a reason[^redundancy] for this
- this means each week is a fresh start (which has pros and cons)

[^redundancy]: You will see the project names of all your RStudio Projects listed in RStudio. Having the week number in the project name keeps you from getting confused on which project you are working on.


### Create an RStudio *project* for the first week


Create a new *RStudio Project* (File > New Project > New Directory > New Project). 

1. Click on "Browse" and switch to *your equivalent* of the folder `` (the project we are about to initiate will be be created in a subdirectory of this folder). Click on "open" to confirm the selection
2. In the field "Directory name", type `week0-rexercise`. This will be the name of your RStudio project and it's parent directory.
3. Check the option "Create a git repository"
4. Click on "Create Project"


**You are all set! You can start working on the tasks of exercise 1.**    




<!-- Create a new .R (or .Rmd) File and divide it into the sections necessary in a classical Data Science workflow. In .R Files, "Sections" can be created within RStudio by adding Comments (`#`) with at least 3 trailing dashes, equal, or pound signs ( `-`, `=`,`#`). In .Rmd Files, their are created with leading pound signs (`#`). -->

<!-- Sections allow code folding (try clicking on the small triangle next to the line number) and facilitate navigation (try the shortcut: `Shift`+`Alt`+`J`). We recommend following sections: -->

<!-- - Loading environment / libraries -->
<!-- - Data import -->
<!-- - Data cleansing -->
<!-- - Data analysis and visualization -->
