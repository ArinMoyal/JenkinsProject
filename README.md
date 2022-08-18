# JenkinsProject
### My RT-ED Jenkins project

In this project, the pipeline runs every time a commit is made.

It first announces which languages were chosen, and prints all the environment variables.

If it is triggered by a commit, it runs with the "LANGUAGE" variable set to "All", which runs all scripts.

If it is triggered manually, you can choose "All", "C", "Python" or "Bash", which run their related scripts, and skips the rest.

After everything is said and done, it creates a log file and stores everything there, including the time and date, build number as well as the user who ran it.


#### Thanks for reading!
