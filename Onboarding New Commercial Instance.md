# Onboarding New Commercial Instance

Documentation: Not started
Doucmentation: Not started
Frequency: On-demand
Last Updated At: August 11, 2022 12:18 AM
Owner: HQ
State: Operational
Type: Commercial
Updated By: Edward So

### Why does the process matter?

<aside>
💡 Onboarding clients is one of the single most important executions we do at GitStart. In order to have a smooth client onboarding the Sales Team works with the Client Success Team to officially handover the client for onboarding. The onboarding of a client at GitStart is in two phases. This doc specifically highlights the internal onboarding of new instance. 

**Phase 1:**
CSM takes the client on an onboarding call. 

**Phase 2:** 
CS-Ops Team onboards the client internally into the GitStart DB and sets client up on all GitStart resources.

</aside>

### Executional Journal

<aside>
💡 CS Team assigns an onboarding task through linear. All linear tickets are clearly scoped and have all necessary information for onboarding.

</aside>

### How to execute the process?

**From Step 1-7, please complete asap when CSMs notified of new client onboarding.** 

1. **[CSM] Create a client bot on Google group**
[https://www.loom.com/share/38e0a53dd79d42f5808db59f36bd239e](https://www.loom.com/share/38e0a53dd79d42f5808db59f36bd239e)
    
    
    - [ ]  Create a Group in [Google Group](https://groups.google.com/), named group "Client: clientname" (e.g. Client: Coherent) / [clientname]@gitstart.com (e.g. coherent@gitstart.com)
    - [ ]  Configure the below settings
    
    ![Untitled](Onboarding%20New%20Commercial%20Instance%2003dca4b4427d47eeaee9d9745c31bc78/Untitled.png)
    
    - [ ]  Add Edward, Sohum, CS Ops, and selected CS Managers / TPMs / Repo-Owners as Group Managers.
    - [ ]  Subscription = “each email” for everyone - except for CS Managers
    
2. **[CS Ops - to automate] On Postico database, add rows sequentially on the following 5 tables – [user_emails], [users], [clients], [user_team_client], [client_users]** 
[https://www.loom.com/share/086a5a727f3d42c2aeb7026eb7724616?sharedAppSource=personal_library](https://www.loom.com/share/086a5a727f3d42c2aeb7026eb7724616?sharedAppSource=personal_library)
****
    - [ ]  [users_emails]: Add row - contact email (e.g. peter@coherent.com.hk)
    - [ ]  [users]: Add row - contact name, email (e.g. Peter Roske, peter@coherent.com.hk)
    - [ ]  [clients]: Add row - id, name, creditBatchSize, onboardedAt (e.g. coherent, coherent, 1000, 2022-02-04 16:28:26.066551+00)
    - [ ]  [client_projects]: Add client_project
    - [ ]  [user_team_clients]: Add row - isOwned, userTeamId, clientID (e.g. True, 5, coherent)
    - [ ]  [client_users]: Add 2 rows using 2 userID - clientID, userID, role (e.g. coherent, Peter's userID, admin & coherent, your userID, internal)
    - [ ]  [client_project_pricing_plan]: Add credit pricing plan id and client_project id
    
3. **[CS Ops]** Create a 1password (1PW) vault for client on GitStart [1password](https://1password.com/) 
[https://www.loom.com/share/555b7d7f75a74520a3858b7825ea2dfe?sharedAppSource=personal_library](https://www.loom.com/share/555b7d7f75a74520a3858b7825ea2dfe?sharedAppSource=personal_library)
    
    
    - [ ]  Create a new vault (e.g. Client: Coherent) and save GitHub + other client login credentials in vault
    
4. **[CS Ops]** Create a client account GitHub bot on [github.com](https://www.github.com) 
[https://www.loom.com/share/1290008f64904492a92511bf8129d150](https://www.loom.com/share/1290008f64904492a92511bf8129d150)

    - [ ]  Username: gitstart-client (e.g. gitstart-coherent) / email: [client]@gitstart.com (e.g. coherent@gitstart.com) / pw: randomly generated and save new login to 1password vault
    - [ ]  Update GitHub settings: Change profile pic to GitStart avatar, update name as GitStart-[Client]
    - [ ]  Enable 2FA Authentication on GitHub: use 1PW desktop app → scanning the QR code → save 2FA recovery code on 1PW GitHub login
    
5. **[CSM]** Open shared slacked channel
[https://www.loom.com/share/43b92d28d7264fd198d7c8a745513767?sharedAppSource=personal_library](https://www.loom.com/share/43b92d28d7264fd198d7c8a745513767?sharedAppSource=personal_library)
    - [ ]  Create a shared slack channel named gitstart-[client]-shared (e.g. gitstart-coherent-shared)
    

6. **[CS Ops - to automate]** Set up slack-standup integration
[https://www.loom.com/share/43b92d28d7264fd198d7c8a745513767?sharedAppSource=personal_library](https://www.loom.com/share/43b92d28d7264fd198d7c8a745513767?sharedAppSource=personal_library)

- [ ]  add @gitstart app into the shared slack channel
- [ ]  then we go to slack_channels table and we should find client-xyz-shared there
- [ ]  then go to slack_standup_channel_mappings and see if the client - channel link is there. if not add it there
    - ps. the internal slack channelSid is mapped at client_projects/channelSid. **External is mapped at `slack_standup_channel_mappings`- please don’t have the two sid be the same one**

1. **[CS Ops]** Create a Google Doc Client retrospective
    - Go to Drive to create a client folder [https://drive.google.com/drive/folders/1CYpw5HJ2XtuCXIuz0OgFgxuJe0UfXDtG?usp=sharing](https://drive.google.com/drive/folders/1CYpw5HJ2XtuCXIuz0OgFgxuJe0UfXDtG?usp=sharing)
    - Copy from template [https://docs.google.com/document/d/1p8IJ2BicUoJgRpIBgoGE1-95OoHj_ykYHP4Vbm8jAys/edit?usp=sharing](https://docs.google.com/document/d/1p8IJ2BicUoJgRpIBgoGE1-95OoHj_ykYHP4Vbm8jAys/edit?usp=sharing)
    - Name Doc - GitStart - [client] Retrospective
    
    [Onboarding For Existing Clients ](Onboarding%20New%20Commercial%20Instance%2003dca4b4427d47eeaee9d9745c31bc78/Onboarding%20For%20Existing%20Clients%20862db3fa477b4c809e121497415ff689.md)
    

**From Step 8, please complete asap when clients send us invites to Git and Ticketing**

1. **[CS Ops]** After we've received access to the client's code repository & Project management:
- [ ]  Setup syncers for Code repository (GitHub OR GitLab)
    
    [Setup GitHub Syncers](https://www.notion.so/Setup-GitHub-Syncers-cc9eac783aeb448aa5f741165b7e1cf5) OR 
    [Onboard GitLab Clients](https://www.notion.so/Onboard-GitLab-Clients-3e84fff8a5ae4443bdfe0bf75e4687ea) 
    
- [ ]  Setup syncers for importing tickets (JIRA OR Linear)
    
    [Setup Jira Syncers](https://www.notion.so/Setup-Jira-Syncers-1bf45041614447828798231e7ac8b426) OR
    [Onboard Linear Clients](https://www.notion.so/Onboard-Linear-Clients-37160b8bb6d64f53b76d07b48fb56d12) 
    
1. **[CS Ops to automate]** Add ticket_source for said project 
    - [ ]  Request TPM for a “prefix” for the tickets