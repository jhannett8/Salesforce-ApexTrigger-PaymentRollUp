Background:
1.	What is Salesforce?
•	Salesforce is the world's #1 customer relationship management (CRM) platform.
2.	What is Apex?
•	Apex is a strongly typed, object-oriented programming language that allows developers to execute flow and transaction control statements on Salesforce servers in conjunction with calls to the API. Using syntax that looks like Java and acts like database stored procedures, Apex enables developers to add business logic to most system events, including button clicks, related record updates, and Visualforce pages. Apex code can be initiated by Web service requests and from triggers on objects.
3.	What is Salesforce Apex Triggers?
•	Apex triggers enable you to perform custom actions before or after events to records in Salesforce, such as insertions, updates, or deletions.


Task:
•	This org is using the 'Kulturra Payment Processor' salesforce extension to process CC payment via a custom Salesforce Site.
•	The Contact object contains a "Total Payment Amount" Field that inherits the value of fw1__Total_Paid_Amount__c within the Kulturra CC Payment Object
•	If the user was to make multiple payments, the "Total Payment Amount" Field would only inherit the latest payment processed; not the rollup for all payments made
•	The resulting value messes with the calculations down stream that incorporated the "Total Payment Amount" Field
Solution:
•	Create a Trigger that fires everytime a payment is made/modified in the org.
•	Trigger should collect a rollup of all payments associated with Contact ID
•	Trigger should update contact's "Total Payment Amount" Field with rollup
