# Intelligent Customer Communication Automation - ICCA activity package for UiPath
Automation First: smoothen communication with customers.

Artificial Intelligence: using state-of-the-art Language Understanding Intelligent Service (LUIS).

Salesforce Integration: facilitating Open Cases in Salesforce Lightning Platform.

Automatic Classification: classify new cases and existing cases in Salesforce. 

Please see the Introduction Youtube video

[![Everything Is AWESOME](https://img.youtube.com/vi/StTqXEQ2l-Y/0.jpg)](https://www.youtube.com/watch?v=StTqXEQ2l-Y "Everything Is AWESOME")

## Getting Started
To get started with the ICCA Activity Pack, you'll need the followings:
1. Salesforce account 
   * 1.1. Edition: Enterprise Edition, Unlimited Edition, Developer Edition, Performance Edition.
      - If you don't have a Salesforce account, please register in the below link for free and testing purpose:
   https://developer.salesforce.com/signup
      - If you already have a Salesforce account, please read the below guide to check your Salesforce edition:
   https://help.salesforce.com/articleView?id=000334996&type=1
   * 1.2. Security Token: we need Salesforce security token to connect Salesforce account via API. Please check the below guide to get your security token which will be sent via email:
   https://webkul.com/blog/security-token-salesforce/
   * 1.3. Create connected apps and obtain Consumer Key and Consumer Secret.
   https://auth0.com/docs/connections/social/salesforce
2. Email setup
   * 2.1. Via Outlook: if you want the robot to read and classify your email via Outlook, please ensure to setup email address in Outlook.
   * 2.2. Via IMAP protocol: please make sure your email account has enabled IMAP access including IMAP mail server and port.
3. LUIS Endpoit URL: register an account [here](https://www.luis.ai/ "luis.ai") and start training your bot.
4. UiPath Orchestrator account (optional but recommended)
Because the activity will use many important credential information for authentication, we recommend you to use UiPath Orchestrator Assets to store those credential information, especially when deploying to production.

## Repository guide
The repository contains 3 folders:
1. [PUADemo2019](https://github.com/tranhuynhthanglong/ICCA/tree/master/PUA2019Demo "PUADemo2019"): We prepared an UiPath project for testing our ICCA activity package. Please download and open in UiPath, so you can immediately use.
2. [Simple LUIS Query Classification](https://github.com/tranhuynhthanglong/ICCA/tree/master/Simple%20LUIS%20Query%20Classification "Simple LUIS Query Classification"): it contains our source UiPath project for each activity in the ICCA package.
3. [Activity package](https://github.com/tranhuynhthanglong/ICCA/tree/master/PUA2019Demo "Activity package"): it contains our ICCA packages named "[Simple_LUIS_Query_Classification.1.0.1-alpha.5.nupkg](https://github.com/tranhuynhthanglong/ICCA/blob/master/Activity%20package/Simple_LUIS_Query_Classification.1.0.1-alpha.5.nupkg "Simple_LUIS_Query_Classification.1.0.1-alpha.5.nupkg")".

## Working with the activity
The below guide will be for [PUADemo2019](https://github.com/tranhuynhthanglong/ICCA/tree/master/Activity%20package "PUADemo2019") folder.
### Config file
We recommend you to utilize the Orchestrator Assets to store our credential information. Then we will use the "Config.xlsx" to guide the robot retreive those credential information.

If you are not familar with Config fle and Orchestrator Assets, we recommend you to study 2 Uipath course: "Level 2 - Orchestrator Trainings" and "Level 3 - RPA Developer Advanced Training".
### Basic activities
1. LUIS classification: with your LUIS AI Endpoint URL and query, this activity will return Top Intent of the query together with Top Intent Scoring, JSON response from LUIS.
2. Outlook mail classification: reading your Outlook mailbox and send mail content to LUIS to classify the type of mail.
3. IMAP mail classification: reading your email via IMAP protocol and send mail content to LUIS to classify the type of mail.
4. Outlook to Salesforce classification: reading your Outlook mailbox and send mail content to LUIS to classify the type of mail. Then, auto creating a new case on Salesforce with "classified type" in "Type" field. If the email is empty or a client's reply to an existing case, it will be skipped.
5. IMAP to Salesforce classification: reading your email via IMAP protocol and send mail content to LUIS to classify the type of mail. Then, auto creating a new case on Salesforce with "classified type" in "Type" field. If the email is empty or a client's reply to an existing case, it will be skipped.
6. Salesforce case classification: when your Salesforce receives cases from different sources such as: email, phone, web, especially if Email-to-Case or Web-to-Case function are enable, you can use this activity to classify the "Type" of new and unclassified cases.
### Activity input arguements
Please have a look at the activity input arguements:

![Activity screenshot](https://github.com/tranhuynhthanglong/ICCA/blob/master/screenshot.png)

* ExcelOutput: Boolean value. Default value = False. If you want to have an excel output listing all processed email and processing result, change value to "True".
* ExcelOutPath (optional): please indicate the full path of output excel inclusive of extension ".xlsx". If it is left blank, output file will be on your desktop with naming convention as "EmailList/CaseList timestamp" with timestamp has format "YYYY-MM-DD HH-mm-ss".
* LUIS_URL: please provide the LUIS AI Endpoint URL which you used to train for classification purpose.
* MailAddress: your email address that the robot will work with.
* MailFolder: your email folder that the robot will work with.
* MailPassword (IMAP only): if you retrieve email via IMAP, please provide email password.
* MailServer (IMAP only): if you retrieve email via IMAP, please provide IMAP mail server.
* MailPort (IMAP only): if you retrieve email via IMAP, please provide IMAP mail port.
* SalesforceConsumerKey: please provide Salesforce Consumer Key, please see Getting Started section to know how to obtain it.
* SalesforceConsumerSecret: please provide Salesforce Consumer Secret, please see Getting Started section to know how to obtain it.
* SalesforceSecurityToken: please provide Salesforce Security Token, please see Getting Started section to know how to obtain it.
* SalesforcePassword: please provide your Salesforce password for login.
* SalesforceUsername: please provide your Salesforce username for login.
* Output MailList/CaseList (optional): the output will be in DataTable type.

## Development note
### Source project
Please check the source UiPath project in this folder [Simple LUIS Query Classification](https://github.com/tranhuynhthanglong/ICCA/tree/master/Simple%20LUIS%20Query%20Classification "Simple LUIS Query Classification").
### Other packages used
Uipath Salesforce Lightning Connector: https://go.uipath.com/component/connector-for-salesforce-lightning-platform
BalaReva.Excel.Activities: https://gallery.uipath.com/packages/BalaReva.Excel.Activities
## Authors
- Long (Leon) Tran - Design / Development / Production / etc
- Tuan Pham - LUIS trainer / etc
- Thu Duong - Development
- Viet Pham - Development
- Cham Le - Development
- Phuong Nguyen - Project Management
## License
This project is licensed under the Apache License 2.0 - see the [LICENSE](https://github.com/tranhuynhthanglong/ICCA/blob/master/LICENSE) file for details.

## Acknowledgments
Thank the wonderful UiPath Team for all useful resources in training courses and in the Webinar for developing Custom Activities.
