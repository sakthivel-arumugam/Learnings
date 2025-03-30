### **Use Case: HR Chatbot for Leave Management**
Objective: To streamline the leave management process by providing instant responses to leave-related queries, automating leave requests and approvals, and maintaining a centralized database of leave records.
**Components Involved:**
1.	Power Virtual Agents: To create the chatbot interface.
2.	Power Automate: To automate workflows and integrate with other systems.
3.	Dataverse: To store and manage data.
4.	Power Apps: Should provide search capabilities to search/get employee leave history. Using Dataverse capabilities.
5.	Power Pages: Should provide search capabilities to search/get employee leave history. Using Dataverse capabilities.
6.	Access Dataverse Web API to access tables in .net/python web api. 

**Flow - Add Knowledge to Agent** 
![Image](https://github.com/user-attachments/assets/ba2a9fb5-8d30-4e0e-8a51-62d877386963)

**Flow - User search query from Agent**
![Image](https://github.com/user-attachments/assets/dd141b86-468b-450f-ada3-954d99740bfc)

**Architecture Diagram:**
![Image](https://github.com/user-attachments/assets/73b343b4-769c-4b85-bf81-14683faadf30)

**Detailed Steps:**
1.	Designing the Chatbot with Power Virtual Agents:
•	Create a New Bot: Start by creating a new bot in Power Virtual Agents.
•	Define Topics: Identify and define topics that the chatbot will handle, such as "Leave Balance Inquiry," "Leave Request," "Leave Approval Status," "Company Leave Policies," etc.
•	Author Conversations: Use the graphical interface to design conversation flows for each topic. Include trigger phrases that will initiate these conversations.
2.	Integrating with Power Automate:
•	Create Flows: Use Power Automate to create flows that the chatbot can trigger. For example, a flow to submit a leave request, a flow to notify managers for approval, or a flow to update leave balances.
•	Connect to Dataverse: Set up connections to Dataverse to read from and write to the database. This allows the chatbot to fetch and update leave records dynamically.
•	Automate Tasks: Automate tasks such as sending leave request notifications, updating leave balances, and generating leave reports.
3.	Setting Up Dataverse:
•	Create Tables: Define tables in Dataverse to store leave records, employee information, leave policies, etc.
•	Data Management: Use Dataverse to manage data integrity and relationships between different entities.
4.	Building the Canvas App:
•	Design the Interface: Use Power Apps to create a canvas app that HR personnel and managers can use to interact with the chatbot and manage leave requests.
•	Integrate with Dataverse: Connect the canvas app to Dataverse to display and update leave records.
•	User Experience: Ensure the app is user-friendly and provides a seamless experience for HR staff and managers.
5.	Testing and Deployment:
•	Test the Chatbot: Thoroughly test the chatbot to ensure it handles all defined topics correctly and integrates smoothly with Power Automate and Dataverse.
•	Gather Feedback: Collect feedback from a small group of users and make necessary adjustments.
•	Deploy: Once testing is complete, deploy the chatbot and canvas app to the entire organization.
Benefits:
•	Efficiency: Automates leave request and approval processes, reducing manual effort.
•	Consistency: Provides consistent responses to leave-related queries.
•	Data Management: Centralizes leave records, making it easier to manage and access.



**Power Virtual Agent:**
https://copilotstudio.microsoft.com/environments/f3a9c683-e734-e79f-b715-3a1c30dfa6db/bots/crd77_leaveAssistant/webchat?__version__=2

**Power Page:**
https://employeeleavemanagement-e626.powerappsportals.com/leave-policy/

**Power Apps - Canvas:**
https://apps.powerapps.com/play/e/f3a9c683-e734-e79f-b715-3a1c30dfa6db/a/3cd8d331-f3fc-4c23-8757-8679cd02dbdc?tenantId=dabd0981-3847-4c61-99f7-8d1958b2eec2&hint=763e1264-cb03-4f9b-9e45-031c7d5e635a&sourcetime=1742617706622

**Azure Portal:**
https://portal.azure.com/#@basavakumarrmoutlook.onmicrosoft.com/resource/subscriptions/2276e794-3271-4193-bcf6-dbb25c698499/resourceGroups/DAI-Team3/providers/Microsoft.Web/sites/EmployeeService/appServices
**Azure App Service:**
https://employeeservice-a6csfubhhsgpgcht.canadacentral-01.azurewebsites.net/swagger/index.html


**HRChat/HRApp for Leave Management System**
Flow1:
	Search Leave Policy information using Power Virtual Agent. 
	Power agent knowledge is boosted with sample leave policy document. 
Flow2:
	Apply Leave using Power Virtual Agent. Custom Topics are created to handle this. 
	Power Automate flow should integrate Dataverse for the data operation. 
	Power Automate flow should sending emails(Submitted, Approved).
	Power Automate flow should Approval process via email. 
Flow3:
	Power Apps(Canvas) should provide search capabilities to search/get employee leave history. Using Dataverse capabilities. 
Flow4:
	Power Pages should provide search capabilities to search/get employee leave history. Using Dataverse capabilities.	
Flow5:
	Use Dataverse API to access LeaveHistory Dataverse table. Created sample web api to consume dataverse api for CURD operations.


