### CORTX Community Scripts

This folder contains a bunch of scripts used by track CORTX Community Metrics.  They are intended to be run using crontab and piped into mail.
They also persist data into pickles and json files as found in the [pickles/ child folder](pickles).  Those pickles should also be automatically updated
using a crontab job.

The main scripts in this folder are the following:
1. **[scrape_metrics.py](scrape_metrics.py)**

    a. This is the main worker program that crawls github and puts a ton of into into pickles
    
    b. It creates two main pickles: one for actions and one for people
    
2. **[get_personal_activity.py](get_personal_activity.py)**

    a. This program will print all known activity by one or community members
    
3. **[cortx_people.py](cortx_people.py)**

    a. This program allows making modifications to the people pickle
    
    b. Use this for example to mark which community members are external or not
    
    c. Run this with the _dump_ flag to see all community members
    
4. **[print_metrics.py](print_metrics.py)**

    a. This program reads the pickles and prints the data from the last time the scrape was done

5. **[cortx_community.py](cortx_community.py)**

    a. This is the module imported by the other python scripts which handles the pickling and various other utility functions
    
6. **[weekly_report.sh](weekly_report.sh)**

    a. A trivial bash script that calls the above and pipes output into mail; intended to be run as a cron job
    
7. **[commit_pickles.sh](commit_pickles.sh)**

    a. A trivial bash script that pushes the pickles into the repo.  Run as part of the above weekly_report.sh
    
For more info, pass '-h' or '--help' to any of the python scripts.
