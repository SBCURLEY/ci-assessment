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
    - weather-data.yml

2.  data folder
    - timestamps folder contains the following:
        - Task 1: Create Directory Structure
        - Task 2: Timestamps
        - Task 3: Formatting Timestamps
        - Task 4: Create Timestamped Files
    -  weather folder contains the following:
        - Task 5: Download Today's Weather Data
        - Task 6: Timestamp the Data
        - Task 7: Write the Script

2. Images folder for README & Tasks 1-7

3. gitignore

4. README.md

5. requirements.txt for any dependent installatons

6. weather.ipynb

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

## References

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