# Perform a query in Splunk
**Project Description:** Using a trial Splunk Cloud account we will upload some default data to simulate a dummy organizaton. Using this test data we will be tasked with identifying whether there are any possible security issues with the mail server. To do so, we  must explore any failed SSH logins for the root account.  

+ For this Project we are tasked with identifying whether there are any possible security issues with the mail server. To do so, you must explore any failed SSH logins for the root account.  

## TASK 1. Create a Trial Splunk Cloud Account
+ To do this visit and follow the instruct <a href='http://docs.splunk.com/Documentation/SplunkCloud/9.1.2312/SearchTutorial/Systemrequirements'>Create a splunk account</a>

## TASK 2. Upload data into splunk
+ To do this visit and follow the instruction <a href='https://docs.splunk.com/Documentation/SplunkCloud/9.1.2312/SearchTutorial/GetthetutorialdataintoSplunk'>Upload data into splunk</a>
+ Once complete you should be looking at this screen below:
  
+ ![image](https://github.com/laroper/splunk-query/assets/165287449/46060378-854a-4f85-818c-b681131b9335)

+ Click start searching and you should then be brought to the Search Summary View:
+ ![image](https://github.com/laroper/splunk-query/assets/165287449/782fa477-9451-4134-a1fc-ea8df17e7a35)
  
| Number | Element | Description |
| :----: | :------ | :---------- |
| 1 | Applications menu | Switch between Splunk applications that you have installed. The current application, Search & Reporting app, is listed. This menu is on the Splunk bar. |
|	2 | Splunk bar |	Edit your Splunk configuration, view system-level messages, and get help on using the product. |
|	3 | Apps bar |	Navigate between the different views in the application you are in. For the Search & Reporting app the views are: Search, Analytics, Datasets, Reports, Alerts, and Dashboards. |
|	4 | Search bar | 	Specify your search criteria. |
|	5 | Time range picker |	Specify the time period for the search, such as the last 30 minutes or yesterday. The default is Last 24 hours. |
|	6 | How to search |	Contains links to the Search Manual and the Search Tutorial. |
|	7 | Workload management (Splunk Cloud Platform only) | Specify which pool to run your search in or to use a policy-based pool. The policies are defined in the Workload Management app. |
|	8 | Search history |	View a list of the searches that you have run. The search history appears after you run your first search. |


## TASK 3. Perform your first query 
+ Our aim is to confirm that the data has been ingested, indexed, and is searchable.

Follow these steps to perform a query:
1. Navigate to Splunk Home. (To return to Splunk Home, click the Splunk Cloud logo on the Splunk Cloud page. At the top right)
   ![Splunk-home-logo](https://github.com/laroper/splunk-query/assets/165287449/576d9037-9674-430d-a225-8951c9906224)
2. Click Search & Reporting. You may close any pop ups that appear.
3. In the search bar, enter your search query: `index=main`
   + This search term specifies the index. An `index` is a repository for data. Here, the index is a single dataset containing events from an `index` named `main`.
4. Select `All Time` from the time range dropdown to search for all the events across all time.
5. Click the search button. Note that the search button is represented by the magnifying glass icon. Your search should retrieve thousands of events.
