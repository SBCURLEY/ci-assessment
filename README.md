# My Computer Infrastructre Assessment Repository

**By Sharon Curley (G00438863@atu.ie)**

![Image from Virtual Metric.com](./images/image_readme.png)

This repository contains my assessment submission for the module Computer Infrastructure.
My github repository link is as follows:

[SBCURLEY/ci-assessment](https://github.com/SBCURLEY/ci-assessment)


## Installation
I had to install the below to get started on this repository
- Python 
- Visual Studio Code
- Cmder
- github Codespace


## Usage
Once the above is installed is complete, you can run the application using the following on the Command Line. `weather.sh` is a shell script, so
bshould be run it using a shell interpreter like `bash` or `sh` (as executable)

`./weather.sh`

## Dependencies
The following libraries are required to execute my notebook:
- `matplotlib.pyplot`: Essential for creating static, animated, and interactive visualizations in Python. It is closely integrated with NumPy and provides a MATLAB-like interface for creating plots and visualizations.
- `numpy`: It contains functionality for multidimensional arrays, high-level mathematical functions such as linear algebra operations.
- `pandas`: Fundamental data analysis and manipulation library built on top of the Python programming language. It offers data structures and operations for manipulating numerical tables and time series.
- `seaborn`: Seaborn is a Python data visualization library based on matplotlib. It provides a high-level interface for drawing attractive and informative statistical graphics.
- `datetime`: The datetime is a built-in module that provides classes for manipulating dates and times

Using python, import the following as per notebook

`import matplotlib.pyplot as plt`

`import numpy as np`

`import pandas as pd`

`import seaborn as sns`

`import datetime`

## Repository Structure

1. .github/workflows

The github folder is the Project for this module. I have defined a GitHub Actions workflow named Automate Weather Script that automates the execution of a script `weather.sh` daily at 10 AM or via manual trigger. It ensures the results of the script are committed and pushed back to the repository for tracking. It allows manual execution if immediate updates are needed outside the scheduled time.
I will go through each line of the script

```
name: Automate Weather Script
```

    This specifies the name of the workflow as it will appear in the Actions tab of the repository.

```
on:
  schedule:
    # Run daily at 10 AM
    - cron: '0 10 * * *'
  workflow_dispatch: 
    inputs: {}
```

    The workflow is triggered on a schedule using a CRON expression (0 10 * * *), which means it will run daily at 10:00 AM UTC.
    CRON syntax:

	• 0: At the 0th minute.

	• 10: At the 10th hour.

	• *: Every day of the month.

	• *: Every month.

	• *: Every day of the week.

The `workflow_dispatch`allows the workflow to be triggered manually by a user via the GitHub Actions UI in the repository.
`inputs` is an optional section for specifying parameters, which in this case is left empty.

*Referecnes*

    • Cron Tab Guru: Cron schedule expressions  (https://crontab.guru/)

    • docs.github.com: Manually running a workflow https://docs.github.com/en/actions/managing-workflow-runs-and-deployments/managing-workflow-runs/manually-running-a-workflow

    • docs.github.com: on.workflow_dispatch.inputs https://docs.github.com/en/actions/writing-workflows/workflow-syntax-for-github-actions#onworkflow_dispatchinputs


    `permissions:`

        `contents: write`

    This grants write access to the repository contents, allowing the workflow to commit and push changes back to the repository.

*Referecnes*
    • docs.github.com: Controlling permissions for GITHUB_TOKEN https://docs.github.com/en/actions/writing-workflows/choosing-what-your-workflow-does/controlling-permissions-for-github_token


    `jobs:`

        `run-weather-script:`

            `runs-on: ubuntu-latest`

    The job name is defined as `run-weather-script`. It runs on a virtual machine. 
    Ubuntu-latest provides a Linux environment with the latest stable Ubuntu version pre-configured with common software.

*Referecnes*
    • github blog: GitHub Actions: Ubuntu-latest workflows will use Ubuntu-22.04 https://github.blog/changelog/2022-11-09-github-actions-ubuntu-latest-workflows-will-use-ubuntu-22-04/
    • docs.github.com: Choosing the runner for a job https://docs.github.com/en/actions/writing-workflows/choosing-where-your-workflow-runs/choosing-the-runner-for-a-job


    `- name: Checkout Repository`

        `uses: actions/checkout@v3`

    Step 1 is to check out the Repository with a description name for the step `Checkout repository`. Uses specifies a reusable action, `actions/checkout@v3`, which checks out the repository’s code. This ensures the workflow has access to the repository’s files, including weather.sh.

*Referecnes*
    • github.com: Checkout https://github.com/actions/checkout   noting that this documentation is using Checkout V4 but Checkout V3 is working in my code. 


   ` - name: Execute weather.sh`

      `run: |`

        `chmod +x weather.sh `

            `./weather.sh`   

    Step 2 is to execute the file.  The `name` indicates that this step executes the `weather.sh` script. The `run` executes shell commands directly in the virtual machine. The command `chmod +x weather.sh` ensures weather.sh is executable by adding the executable permission to the script file and `./weather.sh` runs the script from the current directory.

*Referecnes*
    • itsfoss.com: How to Run a Shell Script in Linux [Essentials Explained for Beginners] https://itsfoss.com/run-shell-script-linux/
  	• Geeks for Geeks: What Does "chmod +x " Do and How to Use It? https://www.geeksforgeeks.org/what-does-chmod-x-do-and-how-to-use-it/


    `- name: Commit and Push Changes`
      `run: |`
        `git config --global user.name "github-actions[bot]"`
        `git config --global user.email "github-actions[bot]@users.noreply.github.com"`
        `git add .`
        `git commit -m "Automated update from weather.sh"`
        `git push`

    Step 3 is to commit and push changes using the label `Commit and Push Changes` 
    Command Details:  

    `git config --global user.name "github-actions[bot]"` 
    This command ensures commits show this name in the repository’s history. This is a placeholder name indicating that the commit was made by the automated workflow, not by a specific user. When someone views the repository's commit history, commits made during this workflow will show "github-actions[bot]" as the author.

    `git config --global user.email "github-actions[bot]@users.noreply.github.com"`
    This sets the email associated with the commits. This is a special email format used by GitHub for commits made by workflows or bots. It ensures that commits are clearly identified as being made by GitHub Actions and not tied to a specific user's personal email.

    `git add` 
    This stages all changes in the working directory for the next commit.

    `git commit -m "Automated update from weather.sh"`
    The above creates a new commit with the specified message.

    `git push`
    Lastly, this pushes the committed changes to the repository’s remote branch.

*Referecnes*
	• Github.com: Git Commit https://github.com/git-guides/git-commit
	• Dev.to: Git Workflow: A Complete Guide for Managing Your Codebase Effectively  Git Workflow: A Complete Guide for Managing Your Codebase Effectively - DEV Community
	• docs.github.com: Guides for Github Actions - https://docs.github.com/en/actions/guides


2.  data folder 
    This folder contains the outputs for the following tasks.
    - timestamps folder contains the following:
        - Task 1: Create Directory Structure
        - Task 2: Timestamps
        - Task 3: Formatting Timestamps
        - Task 4: Create Timestamped Files
    -  weather folder contains the following:
        - Task 5: Download Today's Weather Data
        - Task 6: Timestamp the Data
        - Task 7: Write the Script


3. Images folder for README & Tasks 1-7


4. gitignore


5. README.md


6. requirements.txt for any dependent installations


7. `weather.ipynb`
    Please refer to the Jupyter notebook for detailed explanations of each task
    - Table of Contents
        - Description
        - Explore the Tasks 
            -   Task 1: Create Directory Structure
            -   Task 2: Timestamps
            -   Task 3: Formatting Timestamps
            -   Task 4: Create Timestamped Files
            -   Task 5: Download Today's Weather Data
            -   Task 6: Timestamp the Data
            -   Task 7: Write the Script
            -   Task 9: Pandas
    - References


7. weather.sh
This is the executable program outlined in Task 9. Please refer to the Jupyter notebook for detailed explanation.


## References 
All references are listed with each task in the Jupyter Notebook.

- All lectures 1-10 -  Computer Infrastructure - Ian McLoughlin
- Linus Today: Linux mkdir Command Explained for Beginners (with examples) - https://www.linuxtoday.com/news/linux-mkdir-command-explained-for-beginners-with-examples/
- Linux die.net: mkdir(2) - Linux man page  https://linux.die.net/man/2/mkdir
- Stack Overflow: Uploading a empty folder to github [duplicate] - https://stackoverflow.com/questions/8281322/uploading-a-empty-folder-to-github
- Stack Overflow: How to append output to the end of a text file - https://stackoverflow.com/questions/6207573/how-to-append-output-to-the-end-of-a-text-file
- Linus for Devices: How to append text to the end of a file in Linux - https://www.linuxfordevices.com/tutorials/linux/append-text-to-the-end-of-a-file-in-linux
- Linus for Devices: The cat and more commands in Linux - https://www.linuxfordevices.com/tutorials/linux/cat-more-command-in-linux
- Linusize: Grep Command in Linux - https://linuxize.com/post/how-to-use-grep-command-to-search-files-in-linux/
- Cyberciti: How To Format Date For Display or Use In a Shell Script - https://www.cyberciti.biz/faq/linux-unix-formatting-dates-for-display/
- Squash: Formatting and Displaying Dates with Bash Scripts in Linux - https://www.squash.io/formatting-and-displaying-dates-with-bash-scripts-in-linux/
- Turling.com: Using the Linux Free Command With Examples      https://www.turing.com/kb/how-to-use-the-linux-free-command
- Stack Overflow: How to create a file with todays date in the filename  https://stackoverflow.com/questions/48270960/how-to-create-a-file-with-todays-date-in-the-filename
- Make Rech easier: How to Use Touch Command in Linux    https://www.maketecheasier.com/use-touch-command-in-linux/
- Linus Config :Download file from URL on Linux using command line https://linuxconfig.org/download-file-from-url-on-linux-using-command-line
- How to Geek: How to Use wget, the Ultimate Command Line Downloading Tool  https://www.howtogeek.com/281663/how-to-use-wget-the-ultimate-command-line-downloading-tool/
- Linus Handbook: What's the Difference Between curl and Wget? https://linuxhandbook.com/curl-wget-difference/
- The Linux Code: Demystifying the curl vs wget Debate for Linux Users - History - https://thelinuxcode.com/what-is-the-difference-between-wget-vs-curl/
- Everything Curl - Command line options  https://everything.curl.dev/cmdline/options/index.html
- Askubuntu: How to make a file (e.g. a .sh script) executable, so it can be run from a terminal https://askubuntu.com/questions/229589/how-to-make-a-file-e-g-a-sh-script-executable-so-it-can-be-run-from-a-termi
- Runcloud: Mastering the Echo Command in Linux (with Practical Examples)  https://runcloud.io/blog/echo-command-in-linux
- Digital Ocean: How To View and Update the Linux PATH Environment Variable  https://www.digitalocean.com/community/tutorials/how-to-view-and-update-the-linux-path-environment-variable
- Pandas Pydata: pandas.read_json   https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.read_json.html
- Python Doc: Datetime – Basic date & time types       https://docs.python.org/3/library/datetime.html
- w3schools Python Date    https://www.w3schools.com/python/python_datetime.asp
- Real Python: Using Python datetime to Work With Dates and Times     https://realpython.com/python-datetime/
- Python Tutorial.net: Python datetime     https://www.pythontutorial.net/python-standard-library/python-datetime/
- Dataquest: Python Datetime Tutorial: Manipulate Times, Dates, and Time Spans     https://www.dataquest.io/blog/python-datetime-tutorial/
- Datagy: DateTime in Pandas and Python     https://datagy.io/pandas-datetime/
- Python Doc: Datetime – pandas.to_datetime       https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.to_datetime.html
- Geeks For Geeks: Python | Pandas.to_datetime()       https://www.geeksforgeeks.org/python-pandas-to_datetime/
- Geeks For Geeks: Python | Pandas DataFrame.set_index()       https://www.geeksforgeeks.org/python-pandas-dataframe-set_index/
- Real Python: Visualizing Data in Python With Seaborn    https://realpython.com/python-seaborn/
- Datagy: Seaborn in Python for Data Visualization   https://datagy.io/python-seaborn/
- Seaborn: Choosing color palettes     https://seaborn.pydata.org/tutorial/color_palettes.html



## About Author
- Sharon Curley
  
    My role is a Business Systems Analyst for [Meissner Corporation](https://www.meissner.com/) - a manufacturing company in Castlebar, Co. Mayo. The systems I am supporting currently are Microsoft Dynamics 365 (ERP) for all Meissner entities (Ireland, US, Switzerland, Germany & Italy). I initially started out in functional areas like Customer Service & Supply Chain as I was lucky to be one of the first crew members on board in this company in 2020. I have moved into the IT Dept since March last year. I have a background in SAP - projects & support, so was drawn back into this area when I saw the opportunity arise within Meissner. I have a keen interest in data as when I was a functional user that was the most challenging part of my role - trying to get meaningful data from the systems we use. I have used excel to an advanced level and started with Power BI. I see a lot of opportunities within Meissner to develop in the Data field. I am hoping I will have the skills to do so.

![Meissner](https://www.meissner.com/wp-content/uploads/castlebar-brief-pdf-image.jpg)

- [Git Hub Profile](https://github.com/SBCURLEY "Sharon Curley")

- [Email](mailto:G00438863@atu.ie?subject=Hi "Hi!")