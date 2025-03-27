# # SYSTEM ADMINISTRATION LAB

## Objective
The system administration lab is to demonstrate how to simulate the onboarding process of adding a new user and computer to a network.  This hands-on experience was designed to gain a better understanding of group policies and the onboarding process.

### Skills Learned

- Editing Group Policies
- Adding a computer to the domain
- Adding a user to existing groups and modifying policies
- Creating Shared folders

### Tools Used

- Group Policy
- Network Domains
- Powershell

## Steps
### Joining computer to a Domain
1. Go to control panel > Network and Internet > Network and Sharing Center > Change adapter settings.
![image](https://github.com/user-attachments/assets/6add97e1-846c-48e8-88aa-6caefdf4abc3)
![image](https://github.com/user-attachments/assets/bb5addbc-4b2d-490f-bf3e-a4e9a252fb8f)
2. Select connection, go to properties and double-click ipv4 and select "Use the following DNS server addresses."
![image](https://github.com/user-attachments/assets/6c9ce602-3ec1-47ec-a964-b8eae7fff3c2)
3. Enter the IP address of the server we're connecting to
![image](https://github.com/user-attachments/assets/f489f018-a896-4caf-9e59-aff3b0f6a686)
4. Select OK then close, go back to Control Panel > System and Security > System
5. Select Advanced system settings
![image](https://github.com/user-attachments/assets/b7276686-6ff5-408c-a2e5-9541f6eff481)
6. Select Computer Name > change and select teh Domain radial
![image](https://github.com/user-attachments/assets/361268e3-793e-4bac-8520-00f89f43eacd)
7. Input the domain, we're using "contoso.com"
![image](https://github.com/user-attachments/assets/bbea3d3b-0b38-489d-b9f1-c029a25becb1)
8. Press ok, and enter the password
### Creating a User for the New Hire
1. Go to Active Directory Users and Computers
2. In the "users" folder, click on the button in the upper right to create a new user and assign that user a password.  It is also good practice to check teh box "User must change the password at next logon".  The username and password we will be using is 'Sunshine Skittles' // Popcorn123
![image](https://github.com/user-attachments/assets/68591cc6-7160-4f0d-92e0-1c5784489c6f)
![image](https://github.com/user-attachments/assets/7824b2b0-a6a7-4077-9cdd-5e07577b6cc1)
![image](https://github.com/user-attachments/assets/63f47064-6e67-4489-a2b5-b911fce19355)
### Create a Group with Dept. Name and place user in group







drag & drop screenshots here or use imgur and reference them using imgsrc

Every screenshot should have some text explaining what the screenshot is about.

Example below.

*Ref 1: Network Diagram*
