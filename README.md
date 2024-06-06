# Perform a query in Splunk
**Project Description:** Using a trial Splunk Cloud account we will upload some default data to simulate a dummy organizaton. Using this test data we will be tasked with identifying whether there are any possible security issues with the mail server. To do so, we  must explore any failed SSH logins for the root account.  

+ For this Project we are tasked with identifying whether there are any possible security issues with the mail server. To do so, you must explore any failed SSH logins for the root account.  

## TASK 1. Create a Trial Splunk Cloud Account
+ To do this visit and follow the instruct <a href='http://docs.splunk.com/Documentation/SplunkCloud/9.1.2312/SearchTutorial/Systemrequirements'>Create a splunk account</a>

## TASK 2. Upload data into splunk
+ To do this visit and follow the instruction <a href='https://docs.splunk.com/Documentation/SplunkCloud/9.1.2312/SearchTutorial/GetthetutorialdataintoSplunk'>Upload data into splunk</a>
+ Once complete you should be looking at this screen below:
  
  ![image](https://github.com/laroper/splunk-query/assets/165287449/46060378-854a-4f85-818c-b681131b9335)

+ Click start searching and you should then be brought to the Search Summary View:
  ![image](https://github.com/laroper/splunk-query/assets/165287449/782fa477-9451-4134-a1fc-ea8df17e7a35)
### Search Summary View
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
5. Click the search button.
   
> [!NOTE]
> The search button is represented by the magnifying glass icon. Your search should retrieve thousands of events.

> [!TIP]
> It's a best practice to use short time ranges in your searches because a shorter time range returns results faster and uses fewer resources.

## TASK 4. Examine the search results and fields
When Splunk indexes data, it attaches fields to each event. These fields become part of the searchable index event data. This helps security analysts easily search for and find the specific data they need.
+ For each event the fields are `host`, `source`, and `sourcetype`.
+ Examine the field values by clicking on the field under SELECTED FIELDS. You should observe the following:
  + **host:** The host field specifies the name of the network host from which the event originated. In this search there are five hosts:
    + mailsv - Buttercup Games' mail server. Examine events generated from this host.
    + www1 - This is one of Buttercup Games' web applications.
    + www2 - This is one of Buttercup Games' web applications.
    + www3 - This is one of Buttercup Games' web applications.
    + vendor_sales - Information about Buttercup Games' retail sales.
  + **source:** The source field indicates the file name from which the event originates. You should identify eight sources. Notice `/mailsv/secure.log`, which is a log file that contains information related to authentication and authorization attempts on the mail server.
  + **sourcetype:** The sourcetype determines how data is formatted. You should observe three sourcetypes. Examine secure-2.

![search-](https://github.com/laroper/splunk-query/assets/165287449/20427e18-e830-4346-9f93-075b1c39cf79)

## TASK 5. Refining our search
Because you've been tasked with exploring any failed SSH logins for the root account on the mail server, you'll need to narrow the search results for events from the mail server.

+ Under `SELECTED FIELDS`, click `host` and click `mailsv`.
+ Notice that a new term has been added to the search bar: `index=main host=mailsv`.
+ The search results have narrowed to over 9000 events that are generated by the mail server.

![refine-search](https://github.com/laroper/splunk-query/assets/165287449/ecf5fec1-8ee9-4746-a020-3208405b4c4a)

## TASK 6. Refining even more to find failed SSH logins
Now that you've narrowed your search results to events generated by the mail server, continue to narrow the search to locate any failed SSH logins for the root account. 
1.	Clear the search bar.
2.	Enter `index=main host=mailsv fail* root` into the search bar. This search expands on the search from the previous task and searches for the keyword `fail*`. The wildcard tells Splunk to expand the search term to find other terms that contain the word `fail` such as `failure`, `failed`, etc. Lastly, the keyword `root` searches for any event that contains the term `root`.
3.	Click search.

![refine-search-fail](https://github.com/laroper/splunk-query/assets/165287449/801b1684-451f-4dba-8270-8c197674f3f5)

> [!TIP]
> Splunk highlights search terms in search results to make it easier to identify where the search terms appear in the data.

## Summary 
We used Splunk Cloud to perform a search and investigation. And was able to:
+ Upload sample log data
+ Search through indexed data
+ Evaluate search results
+ Identify different data sources
+ Locate failed SSH login(s) for the root account







