# Perform a query in Splunk
**Project Description:** Using a trial Splunk Cloud account we will upload some default data to simulate a dummy organizaton. Using this test data we will be tasked with identifying whether there are any possible security issues with the mail server. To do so, we  must explore any failed SSH logins for the root account.  

+ For this Project we are tasked with identifying whether there are any possible security issues with the mail server. To do so, you must explore any failed SSH logins for the root account.  

## TASK 1. Create a Trial Splunk Cloud Account
+ To do this visit and follow the instruct <a href='http://docs.splunk.com/Documentation/SplunkCloud/9.1.2312/SearchTutorial/Systemrequirements'>Create a splunk account</a>

## TASK 2. Upload data into splunk
+ To do this visit and follow the instruction <a href='https://docs.splunk.com/Documentation/SplunkCloud/9.1.2312/SearchTutorial/GetthetutorialdataintoSplunk'>Upload data into splunk</a>
+ Once complete you should be looking at this screen below:
  
![image](https://github.com/laroper/splunk-query/assets/165287449/46060378-854a-4f85-818c-b681131b9335)

## TASK 3. Perform your first query 
+ Our aim is to confirm that the data has been ingested, indexed, and is searchable.

Follow these steps to perform a query:
1. Navigate to Splunk Home. (To return to Splunk Home, click the Splunk Cloud logo on the Splunk Cloud page.)
2. Click Search & Reporting. You may close any pop ups that appear.
3. In the search bar,  enter your search query:index=mainThis search term specifies the index. An index is a repository for data. Here, the index is a single dataset containing events from an index named main.
4. Select All Time from the time range dropdown to search for all the events across all time.
5. Click the search button. Note that the search button is represented by the magnifying glass icon. Your search should retrieve thousands of events.
