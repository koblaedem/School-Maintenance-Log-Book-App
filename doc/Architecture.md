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

### Retrieval/Search Flow:
![image](https://github.com/koblaedem/School-Maintenance-Log-Book-App/blob/main/arch_diagram2.png)
##### Comments: When the maintenance team decides to query the database in search of a user, it retrieves data from the list directly without the need for a flow.

### Database Structure:
![image](https://github.com/koblaedem/School-Maintenance-Log-Book-App/blob/main/arch_diagram3.png)
