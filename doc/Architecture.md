# Solution Overview
This application is built leveraging Microsoft Platform technologies, providing a centralised maintenance reporting solution for the school.

The application consists of three components:
- Power App ( for the user interface )
- Power Automate ( Workflow processing and zero trust implementation )
- SharePoint List ( Backend Data Storage )

# Architecture Diagram
### Submission Flow:
![image](https://github.com/koblaedem/School-Maintenance-Log-Book-App/blob/main/arch_diagram1.png)
#### Comments: When user hits submit button the action is completed using the flow acting as a connection point to the database. 

### Retrieval/Search Flow:
![image](https://github.com/koblaedem/School-Maintenance-Log-Book-App/blob/main/arch_diagram2.png)
### Comments: When the maintenance team decides to query the database in search of a user, it retrieves data from the list directly without the need for a flow.

### Database Structure:
![image](https://github.com/koblaedem/School-Maintenance-Log-Book-App/blob/main/arch_diagram3.png)
