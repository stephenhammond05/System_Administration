# # SYSTEM ADMINISTRATION LAB

## Objective
The system administration lab is to demonstrate how to simulate the onboarding process of adding a new user and computer to a network.  This hands-on experience was designed to gain a better understanding of group policies and the onboarding process.  In this exercise I will be creating a playbook to show future employees how to onboard new users with their access rights.

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
2. In the "users" folder, click on the button in the upper right to create a new user and assign that user a password.  It is also good practice to check the box "User must change the password at next logon".  The username and password we will be using is 'Sunshine Skittles' // Popcorn123
![image](https://github.com/user-attachments/assets/68591cc6-7160-4f0d-92e0-1c5784489c6f)
![image](https://github.com/user-attachments/assets/7824b2b0-a6a7-4077-9cdd-5e07577b6cc1)
![image](https://github.com/user-attachments/assets/63f47064-6e67-4489-a2b5-b911fce19355)
### Create a Group with Dept. Name and place user in group
1. Create a group named HR
2. While in ADUC click the icon at teh top labeled create group with the current container.
![image](https://github.com/user-attachments/assets/2de095ad-5544-46f6-bca7-7d2a8919d5b5)
![image](https://github.com/user-attachments/assets/96d63d67-57b2-4bd5-89a4-104454402e6e)
3. right click the username and go to properties > Member of > Add
![image](https://github.com/user-attachments/assets/8477e68a-8dc3-4a80-a5cc-032ce11a7aec)
![image](https://github.com/user-attachments/assets/16ce1261-63f0-4285-b943-5d78f8063242)
4. Enter HR in the box and select "Check Names" the OK
![image](https://github.com/user-attachments/assets/9c3466a7-651e-4f45-9c41-25d6d5ece596)
### Create a Shared Text Document
1. On the server computer, go to cocuments and create a new folder named "HR"
2. Create an empty file named text.txt in the new HR folder
3. Right click the text file and select "Share with" > "Specific People"
![image](https://github.com/user-attachments/assets/b2efc667-1092-4640-a956-c546d67f8622)
4. In the dialogue box, type in "HR" > add > select read/write
![image](https://github.com/user-attachments/assets/ef20c40c-ba04-44ca-9903-f6a4666e752d)
![image](https://github.com/user-attachments/assets/7900016b-386d-41bf-9c04-46ccfa38ce7e)
### Create an OU 
1. Go back to ADUC then domain > "Create a new organizational unit in the current container"
![image](https://github.com/user-attachments/assets/5d81146e-cdac-4a40-8c6d-39fa90453793)
2. Input the Department name "HR" and select "OK"
3. Drag the objects "Sunshine Skittles", the computer(Desktop-2), and the group(HR) into the HR folder that was just created.
![image](https://github.com/user-attachments/assets/4a8065c1-08c7-4893-8fb3-abaa4593cca2)
![image](https://github.com/user-attachments/assets/98a0d892-2108-42b6-a30d-364f5842147c)
4. Attach a GPO(Group Policy Object) to the OU that was just created by going to "Group Policy Management"
5. Right click the folder we're adding the GPO to (the HR folder), and select "Create a GPO in this Domain, and Link it here..."
![image](https://github.com/user-attachments/assets/0926f551-5646-4212-a951-3b1030658921)
6. Make the object name "HR rules" and select OK
### Edit the GPO rules
1. Right click the GPO and edit
![image](https://github.com/user-attachments/assets/207eb207-3d95-4648-89f8-31a6395df414)
2. Go to Computer Configuration>Policies>Windows Settings> Security Settings > Local Policies > Security options and find the “Interactive logon: Message text for users attempting to log on” and “Interactive logon: Message title for users attempting to log on”
![image](https://github.com/user-attachments/assets/c06238bc-fedf-4443-a358-73be95186040)
3. In the first one text, check the box for “Define policy setting” and write “Do Not Install Unauthorized Programs on this Computer”, and on the second one for title, check “Define policy setting” and write “Do Not Install Unauthorized Programs on this Computer”.
![image](https://github.com/user-attachments/assets/4d618647-269d-4f63-96ad-9b2c4d40fc85)
![image](https://github.com/user-attachments/assets/86287f16-44f9-4f73-979f-f27e5d66de34)
4. Click Apply and OK on both.
5. To find the Command Prompt GPO, go to User Configuration > Policies > Administrative Templates > System and go to “Prevent Access to the command prompt”
6. Click the Enabled radial, then apply, then OK
![image](https://github.com/user-attachments/assets/a6dd5c3e-975c-4802-bcca-ea7ac8f960cd)
![image](https://github.com/user-attachments/assets/2f76b124-21cb-42af-be49-e53dcf30dec2)
Get the script from <a href="https://github.com/stephenhammond05/mapdrive.git" target="_blank">here</a>
7. Place script in Logon folder located at "\\contoso.com\SysVol\contoso.com\Policies\{policy id}\User\Scripts\Logon"
8. Go to User Configuration > Policies > Windows Settings > Scripts(Logon/Logoff)
9. Right Click Logon and go to properties, then add the script named mapdrive.ps1 and select open > OK > Apply Changes > OK
![image](https://github.com/user-attachments/assets/0d6c0734-b72d-4cb9-8b55-51136bd52765)
Go to User Configuration > Windows Settings > Administrative Templates > Start Menu and Taskbar and go to "Remove Run Menu from Start Menu"
Right-click and go edit > Enable, then Apply, OK
![image](https://github.com/user-attachments/assets/54db21a5-22c1-4a87-bf27-e76a1ffd39c2)
Close all of the editing windows and go to Command Prompt and type in "gpupdate /force" to put all the new settings into effect

