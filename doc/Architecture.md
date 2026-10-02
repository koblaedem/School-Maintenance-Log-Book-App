# Solution Overview
This application is built leveraging Microsoft Platform technologies, providing a centralised maintenance reporting solution for the school.

The application consists of three components:
- Power App ( for the user interface )
- Power Automate ( Workflow processing and zero trust implementation )
- SharePoint List ( Backend Data Storage )

# Architecture Diagram
### Submission Flow:
![image](https://github.com/koblaedem/School-Maintenance-Log-Book-App/blob/main/arch_diagram1.png)
The submission process allows school staff to report maintenance issues through the Power App.
#### Process:
1. Staff member enters maintenance details.
2. Staff member selects **Report Issue**.
3. Power Apps triggers a Power Automate flow.
4. Power Automate validates and processes the submission.
5. A new maintenance record is created within the SharePoint List.
#### Purpose
Power Automate acts as the controlled submission layer between the user interface and backend data store.
This approach centralises business logic and supports a more secure design by preventing direct write access to the backend data source.

---
### Retrieval/Search Flow:
![image](https://github.com/koblaedem/School-Maintenance-Log-Book-App/blob/main/arch_diagram2.png)
The retrieval process allows maintenance staff to search for and review existing maintenance requests.
#### Process
1. User enters a Staff Name or Issue Number.
2. Power Apps queries the SharePoint List.
3. Matching records are returned.
4. Results are displayed within the application.
#### Purpose
This design allows maintenance staff to retrieve information quickly without requiring an intermediate workflow process.
As the operation is read-only, Power Apps can interact directly with SharePoint for improved performance and reduced complexity.

---
### Database Structure:
![image](https://github.com/koblaedem/School-Maintenance-Log-Book-App/blob/main/database.png)
The database using list consists of the following columns:
* ID: this creates an auto-generated numerical value that is used to easily identify the data submitted. It assists with data retrieval.
* Staff Name: this column stores the submitter name. The submitter simply enters their first name and a dropdown would displays their name as stored in Entra ID.
* Location: this column allows user to define where issue took effect.
* Description: this column allows uses to further describe the issue that needs attention.
* Status: this column allows relevant staff responsible for maintenance with permission to track the progress of issues reported. Either New, Pending, or Resolved.
* Date Reported: this column auto generated the date and time the issue was submitted. 

