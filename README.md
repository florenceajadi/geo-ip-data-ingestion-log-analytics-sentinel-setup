<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Geo IP Data Ingestion Log Analytics Sentinel Setup</h1>
In this tutorial, we are sharing out resources over the network and creating file shares to allow read, write, or deny access to individual users or groups. <br />


<h2>Video Demonstration</h2>

- ### [Network Files Shares and Permissions](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- File Folders


<h2>Operating Systems Used </h2>

- Windows 10 (21H2)


<h2>High-Level Steps</h2>

- Created a Log Analytics Workspace (LAW) 
- Add Microsoft Sentinel to the new workspace
- Created the geoip watchlist
- 

<h2>Actions and Observations</h2>

<p>
<img src="https://github.com/user-attachments/assets/8a55d250-cbfe-4f1a-a68c-3db3c0b5f0d1" height="80%" width="80%" />
</p>

<br />

<p>
<img src="https://github.com/user-attachments/assets/43ea280b-70a8-4178-8c8b-3bf0e28336e4" height="80%" width="80%""/>
 
</p>
<p>
Create a Log Analytics Workspace (LAW) named LAW-CC-Security-0x and added Microsoft Sentinel to a workspace.
</p>
<p>
  <img src="https://github.com/user-attachments/assets/2cf7e8ad-0f13-4cc4-ac5c-2a67ba6cc360" height="80%" width="80%" />
  <img src="https://github.com/user-attachments/assets/fc1dc46b-6666-4cf1-84d2-05b0c448b793" height="80%" width="80%" />
</p>
<p> Created the geoip watchlist  and uploaded a geoip-summarized.csv file</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/80e434b4-385d-4e81-9dd0-a47e2dc60edf" height="80%" width="80%" />
 <img src="https://github.com/user-attachments/assets/ec6bf52e-5c34-4ad3-b725-e16350862347" height="80%" width="80%" />
<img src="https://github.com/user-attachments/assets/2d8ecb9d-c9c6-4693-9997-a9f7875b7c9b" height="80%" width="80%" />
   <img src="" height="80%" width="80%" />
</p>
<p>

</p>
<p>
  <img src="" height="80%" width="80%" />
  <img src="" height="80%" width="80%" />
  <img src="" height="80%" width="80%" />
</p>
<p>
  Able to set all Domain Users to read-access to permission level to read only and write-access (read/write). Able to set all Domain Admins to no-access with permission level set to read/write.
</p>
<br />

<p>
<img src="" height="80%" width="80%" />
</p>
<p>
  No-access permission is only for Domain Admins. Since I'm logged into my user BAT.MEX on Client-1 VM, I was denied access.
</p>
<p>
<img src="" height="80%" width="80%" />
</p>
<p>
  Although as a Domain user BAT.MEX, I am granted access to read-access folder, but when trying to create a txt.file, I was unable to since Domain Users are granted read-only access.
</p>

<p>
<img src="" height="80%" width="80%" />
</p>
<p>
  write-access was set to read/write for Domain Users. So as someone like BAT.MEX is able to access, read, and write in the folder.
</p>

<p>
<img src="" height="80%" width="80%" />
</p>

<p>
  On DC-1 as an admin, I'm able to read and write on the read-access folder.
  
</p>

<p><img src="" height="80%" width="80%" />
  
</p>
<p>
  On DC-1, I created an Organizational Unit called SECURITY GROUPS and in that group, I was ale to create ACCOUNTANTS.
</p>
<p>
  <img src="https://github.com/user-attachments/assets/0c81f603-7b1b-4a4b-9dba-e7c47fb0cbe9" height="80%" width="80%" />

</p>
<p>
  In my DC-1 VM, I'm able to grant access in the accountants folder to ACCOUNTANTS with a permission level to read/write.
</p>

<br />
<p>
  <img src="https://github.com/user-attachments/assets/8513e1b5-c7cb-47e2-b9f6-bf988ac2fb39" height="80%" width="80%" />
  
</p>
<p>
  Logging back into Client-1 VM on user BAT.MEX, I was unable to access accountants folder due to it only being for accountants.
</p>
<p>
  <img src="https://github.com/user-attachments/assets/6a6585f3-ba19-4cf8-9e17-bd74053b1b14" height="80%" width="80%" />
</p>
<p>
  Created and granted access for user BAT.MEX for accountants folder. 
</p>

<p>
  <img src="https://github.com/user-attachments/assets/7469fa36-9db8-4c41-ac10-a411d0de5604" height="80%" width="80%" />
</p>
<p>Permission and access granted for user BAT.MEX on Client-1 VM. BAT.MEX is now able to read/write on Accountants. </p>
