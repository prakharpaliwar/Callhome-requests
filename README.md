# callhome-requests
Just a basic demo of project
# About Call Home
## What is Call Home?
Call Home is a framework for collecting data from any ORACLE Cerner nodes with Olympus presence and centralizing that data. 
Here is the general flow of how data is retrieved with Call Home:
1. "Call Home Requests" are distributed to all nodes with Olympus presence. Call Home Requests schedule themselves, and 
are akin to cron jobs.
1. When a Call Home Request executes, it runs its script on its node and sends the output (the stdout) of the script 
to CCTS, which forwards the data to the Wolfe Ingestion Platform.
1. Data is read off of the Wolfe Ingestion Platform into one of a few destinations 
(ESM Vertica, Tableau, LightsOn, and IBM Streams are common destinations)
1. Users can now use one of those platforms to analyze or build views for the data.

## Common Use Cases
* Scheduling a SQL query to run across all Millennium DBs on a monthly, weekly, or daily basis.
* Collecting the contents of structured files such as CSV, JSON, or XML from a large number of nodes.
* Collecting the output of a shell command from all Cerner's Linux and/or AIX nodes. Or collecting the output of a powershell
