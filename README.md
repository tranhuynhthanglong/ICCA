# Intelligent Customer Communication Automation - ICCA activity package for UiPath
Automation First: smoothen the communication with customers. 
Artificial Intelligent: using state-of-the art Language Understanding Service. 
Salesforce Integration: facilitating Open Cases in Salesforce Lightning Platform. 
Automatically Categorizes: new cases and existing cases in Salesforce. 
Please see the Introduction Youtube video:


## Getting Started
To get started with the DocuSign Activiy Pack, you'll need the followings:
1. Salesforce account
1.1. Edition: Enterprise Edition, Unlimited Edition, Developer Edition, Performance Edition
If you don't have a Salesforce account, please register in the below link for free and testing purpose:
https://developer.salesforce.com/signup
If you already have a Salesforce account, please read the below guide to check your Salesforce edition:
https://help.salesforce.com/articleView?id=000334996&type=1
1.2. Security Token: we need Salesforce security token to connect Salesforce account via API. Please check the below guide to get your security token which will be sent via email:
https://webkul.com/blog/security-token-salesforce/
1.3. Create connected apps and obtain Consumer Key and Consumer Secret.
https://auth0.com/docs/connections/social/salesforce
2. Email setup
2.1. Via Outlook: if you want the robot to read and classify your email via Outlook, please ensure to setup email address in Outlook.
2.2. Via IMAP protocol: please make sure your email account has enabled IMAP access including IMAP mail server and port.
3. UiPath Orchestrator account (optional but recommended)
Because the activity will use many important credential information for authentication, we recommend you to use UiPath Orchestrator Assets to store those credential information, especially when deploying to production.

## Repository guide
The repository contains 3 folders:
1. PUADemo2019: We prepared an UiPath project for testing our ICCA activity package. Please download and open in UiPath, so you can immediately use.
2. Simple LUIS Query Classification: it contains our source UiPath project for each activity in the ICCA package.
3. ICCA Activity Package: it contains our ICCA packages named "Simple_LUIS_Query_Classification.1.0.1-alpha.5.nupkg".

### Working with the activity
