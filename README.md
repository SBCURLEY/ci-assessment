# My Assessment Repository

**By Sharon Curley (G00438863@atu.ie)**

This repository contains my assessment  submission for the module Computer Infrastructure

## Getting Started

1. Clone the repository.

2. Run the Code
>>>>>>> 7724fa03419d27c1527ae0c7c4c116de9a3bf9d1




Tasks (40%)
Complete all tasks in your repository. Remember to commit and push your work regularly.

In Task 8, you will write a report summarizing your work on Tasks 1 to 7, so keep notes as you go. You may find it helpful to draft parts of Task 8 while working through the other tasks.

Task 1: Create Directory Structure
Using the command line, create a directory (that is, a folder) named data at the root of your repository. Inside data, create two subdirectories: timestamps and weather.

I created a folder called data with two sub folders mkdir -p data\weather and a second command mkdir -p data\timestamps. To enable a push to Gitbub, I created test files
in the two subfolders

![alt text](task_01.png)

References
- Linus Today - Linux mkdir Command Explained for Beginners (with examples)       https://www.linuxtoday.com/news/linux-mkdir-command-explained-for-beginners-with-examples/
- die.net -  mkdir(2) - Linux man page    https://linux.die.net/man/2/mkdir
- Stack Overflow:  Uploading a empty folder to github [duplicate]  https://stackoverflow.com/questions/8281322/uploading-a-empty-folder-to-github


Task 2: Timestamps
Navigate to the data/timestamps directory. Use the date command to output the current date and time, appending the output to a file named now.txt. Make sure to use the >> operator to append (not overwrite) the file. Repeat this step ten times, then use the more command to verify that now.txt has the expected content.

Using the following function, I was able to output the current date & time to a new folder called “now.txt”
date +"%Y%m%d_%H%M%S" >> now.txt
I ran the code 10 times ensuring the correct operator was being used. (>> append as opposed to > override)
I check the contents of now.txt using
cat now.txt
more now.txt

The cat command outputs a file without a pause. So the entire contents of the file are output to the terminal and the terminal scrolls to the end of the file. With the more command, the output stops at the end of the terminal screen allowing you to scroll down using the space key (to scroll a page) or the enter key (scroll line by line) on your keyboard.

As I generated the code 10 times, each datetime was updated 10 times to now.txt

![alt text](task_02.png)

References
- Stack Overflow  How to append output to the end of a text file   https://stackoverflow.com/questions/6207573/how-to-append-output-to-the-end-of-a-text-file
- Linus for Devices: How to append text to the end of a file in Linux    https://www.linuxfordevices.com/tutorials/linux/append-text-to-the-end-of-a-file-in-linux
- Linus for Devices: The cat and more commands in Linux    https://www.linuxfordevices.com/tutorials/linux/cat-more-command-in-linux


Task 3: Formatting Timestamps
Run the date command again, but this time format the output using YYYYmmdd_HHMMSS (e.g., 20261114_130003 for 1:00:03 PM on November 14, 2026). Refer to the date man page (using man date) for more formatting options. (Press q to exit the man page). Append the formatted output to a file named formatted.txt.

Using the following function, I was able to output the current date & time to a new folder called “formatted.txt”
date +"%Y%m%d_%H%M%S" >> formatted.txt

References
- Linusize:Grep Command in Linux    https://linuxize.com/post/how-to-use-grep-command-to-search-files-in-linux/


Task 4: Create Timestamped Files
Use the touch command to create an empty file with a name in the YYYYmmdd_HHMMSS.txt format. You can achieve this by embedding your date command in backticks ` into the touch command. You should no longer use redirection (>>) in this step.

I used the touch command to create an empty file with a name in the YYYYmmdd_HHMMSS.txt format. 
$ touch `date +"%Y%m%d_%H%M%S.txt"`

References
- Turling.com: Using the Linux Free Command With Examples      https://www.turing.com/kb/how-to-use-the-linux-free-command
- Stack Overflow: How to create a file with todays date in the filename  https://stackoverflow.com/questions/48270960/how-to-create-a-file-with-todays-date-in-the-filename
- Make Rech easier: How to Use Touch Command in Linux    https://www.maketecheasier.com/use-touch-command-in-linux/


Task 5: Download Today's Weather Data
Change to the data/weather directory. Download the latest weather data for the Athenry weather station from Met Eireann using wget. Use the -O <filename> option to save the file as weather.json. The data can be found at this URL:

https://prodapi.metweb.ie/observations/athenry/today.


Task 6: Timestamp the Data
Modify the command from Task 5 to save the downloaded file with a timestamped name in the format YYYYmmdd_HHMMSS.json.

Task 7: Write the Script
Write a bash script called weather.sh in the root of your repository. This script should automate the process from Task 6, saving the weather data to the data/weather directory. Make the script executable and test it by running it.

Task 8: Notebook
Create a notebook called weather.ipynb at the root of your repository. In this notebook, write a brief report explaining how you completed Tasks 1 to 7. Provide short descriptions of the commands used in each task and explain their role in completing the tasks.

Task 9: pandas
In your weather.ipynb notebook, use the pandas function read_json() to load in any one of the weather data files you have downloaded with your script. Examine and summarize the data. Use the information provided data.gov.ie to write a short explanation of what the data set contains.

Project (40%)
In this project, you will automate your weather.sh script to run daily and push the new data to your repository. The following steps will create the necessary GitHub Actions workflow.

    1. Create a GitHub Actions Workflow: In your repository, create a folder called .github/workflows/ (if it doesn't already exist). Inside this folder, create a file called weather-data.yml. This file will define the GitHub Actions workflow.
    2. Run Daily at 10am: Use the schedule event with cron to set the script to run once a day at 10am. Include also the workflow_dispatch event so you can test the workflow.
    3. Use a Linux Virtual Machine In the workflow file, specify that a Ubuntu virtual machine should be used to run the action.
    4. Clone the Repository Have the workflow clone your repository.
    5. Execute the weather.sh Script Add a step that runs your weather.sh script.
    6. Commit and Push Changes Back to the Repository Finally, configure the workflow to commit the new weather data and push those changes back to your repository.
    7. Test the Workflow Commit and push the workflow to your repository. Check the logs in GitHub to ensure that the weather.sh script runs correctly, that new data is being committed.

From <https://github.com/ianmcloughlin/2425_computer_infrastructure?tab=readme-ov-file#tasks-40