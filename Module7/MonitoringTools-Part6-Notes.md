## How To Setup Dynatrace?

### Application Environment

This is where the application will be deployed and it will handle the user requests.

### Dynatrace Environment

This is the environment where Dynatrace monitor the applications and manage the monitored data.

OneAgent wll be downloaded from Dynatrace environment and installed on each server.

OneAgent will send the monitored data regularly to Dynatrace Environment.

Dynatrace users (Administrators / Application Users) will retrieve the data from Dynatrace environment using Dynatrace UI.

Dynatrace is not free for use.

### Dynatrace Setup process
 - Create Account
 - Download the OneAgent from Dynatrace SaaS
 - Install the agent on the server

### Dynatrace Demo Application

easyTravel is a multi-tier application implemented in .NET and Java.
It provides a webportal for users and travel agencies where they can perform different operations.

Reference: https://community.dynatrace.com/t5/Start-with-Dynatrace/easyTravel-Documentation-and-Download/m-p/181271
