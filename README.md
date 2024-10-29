# About 
The file is run in WSL (i.e., Windows Subsystem for Linux) .
The main file `java_cron.yml` includes the following tasks:
- Installing required JDK (in this case is JDK 17) for the Java application
- Creating a Linux cron job for running the Java program every 3rd minute (03, 13, 23, 33, 43, 53)

# Requirements
- Linux (or Linux subsystem)
- ansible playbook package 
# How to use 
- Clone the whole project (or just simply donwload the main file) to a directory. \
Since I was using WSL, I will open that directory using WSL.  
- Open `java_cron.yml` in the editor nano and specify the path that leads to the `.jar` file in (in my case, it's `"/mnt/c/ProgramData/Jenkins/.jenkins/workspace/cicd/target/WebApplication-0.0.1-SNAPSHOT.jar"`).
- Run `ansible-playbook java_cron.yml --ask-become-pass` (since I did not include the password as plain text in the file)
- The cron job is now scheduled. In order to check the current jobs, `sudo crontab -u root -l`

# Reference
https://www.ibm.com/docs/fi/aix/7.1?topic=c-crontab-command \
https://www.cyberciti.biz/faq/how-do-i-add-jobs-to-cron-under-linux-or-unix-oses/
