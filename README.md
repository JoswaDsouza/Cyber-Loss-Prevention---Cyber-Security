### Documentation is included in the Documentation folder ###

[REFrameWork Documentation](https://github.com/UiPath/ReFrameWork/blob/master/Documentation/REFramework%20documentation.pdf)

### REFrameWork Template ###
**Robotic Enterprise Framework**

* Built on top of *Transactional Business Process* template
* Uses *State Machine* layout for the phases of automation project
* Offers high level logging, exception handling and recovery
* Keeps external settings in *Config.xlsx* file and Orchestrator assets
* Pulls credentials from Orchestrator assets and *Windows Credential Manager*
* Gets transaction data from Orchestrator queue and updates back status
* Takes screenshots in case of system exceptions


### How It Works ###

1. **INITIALIZE PROCESS**
 + ./Framework/*InitiAllSettings* - Load configuration data from Config.xlsx file and from assets
 + ./Framework/*GetAppCredential* - Retrieve credentials from Orchestrator assets or local Windows Credential Manager
 + ./Framework/*InitiAllApplications* - Open and login to applications used throughout the process

2. **GET TRANSACTION DATA**
 + ./Framework/*GetTransactionData* - Fetches transactions from an Orchestrator queue defined by Config("OrchestratorQueueName") or any other configured data source

3. **PROCESS TRANSACTION**
 + *Process* - Process trasaction and invoke other workflows related to the process being automated 
 + ./Framework/*SetTransactionStatus* - Updates the status of the processed transaction (Orchestrator transactions by default): Success, Business Rule Exception or System Exception

4. **END PROCESS**
 + ./Framework/*CloseAllApplications* - Logs out and closes applications used throughout the process


### For New Project ###

1. Check the Config.xlsx file and add/customize any required fields and values
2. Implement InitiAllApplications.xaml and CloseAllApplicatoins.xaml workflows, linking them in the Config.xlsx fields
3. Implement GetTransactionData.xaml and SetTransactionStatus.xaml according to the transaction type being used (Orchestrator queues by default)
4. Implement Process.xaml workflow and invoke other workflows related to the process being automated


Cyber Loss Prevention
![image](https://github.com/JoswaDsouza/Cyber-Loss-Prevention---Cyber-Security/assets/117136563/d4ee9824-d44f-499b-9781-44ebe1c81eed)

Credit card fraud accounted for $28.58 Billion in losses for global financial institutions in 2020 alone. To combat rampant fraud, the cyber loss prevention team at Eagle One Financial is taking a non-traditional approach to combat losses: scraping credit card dumps from dark web pages in an effort to try to identify compromised accounts.
Ryan Club - The Dark Web
Click the link below to be taken to Ryans Club - a simulated dark web location that recently published a large dump of stolen credit card numbers.
Scrape the available listings from Credit Card Dump 349473
The data is incomplete (because they want you to buy it) - so run the available details for each card against the Eagle One Financial Customer DB
If a match is found, log the Eagle One Financial Customer ID, First Name, Last Name, Full Card Number, CVV, and Brand to the account cancellations CSV (template below)
Once you've captured each user's details in the CSV, upload the file using the uploader below to validate your results
NOTE: Just like many pages on the dark web, Ryan's Club can't be accessed directly by URL, You MUST click the link below to launch Ryan's club - as the data loaded each time is randomized and tied to this page.
The data available for each stolen credit card is incomplete (because they want you to buy it) - so scrape the listings on their page and try to identify how many (if any) of the cards listed were issued.

Eagle One Financial - Customer Database
The database provided below is a SQLite DB. It contains all of Eagle One Financial's customers - with their data spread across 2 tables. (Note: if you want to explore the data/table structure a bit more, you can download SQLiteStudio to take a look at how the database is set up or you can review the database diagram here)

The customer_details table contains basic customer details like name, customer ID, and address
The card_details table contains the full credit card details for each customer, and is linked to the customer_details table by foreign key of customer ID.
Since the data available in Ryan's Club isn't complete, you'll need to figure out how to best check for matching customers using the data that's available.

Eagle One Financial - Cancellations CSV Template
Eagle One Financial's objective is to eliminate/reduce the financial impact of fraudlent transactions by identifying and proactively cancelling/reissuing new cards to impacted customers. For each impacted customer you identify:

Download and enter their details in the cancellations CSV below
Upload the file below once all impacted customer details have been entered into the CSV
The uploaded file will then be validated to provide you with a score on how quickly/accurately you were able to identify the exposed customer's details.


