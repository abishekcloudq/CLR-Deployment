## Check-list to create Prod deployment process

 - First, [ADO Ticket](ADO_Ticket.png)  needs to be created for prod deployment process.
 
	 ![[Pasted image 20250221142044.png]]
## Deployment Cycle

> [!info] DEPLOYMENT CYCLE
> -  APCO-IPL ORG - Every **==Tuesday==** and ==**Friday**== 
> - OGNE -ORG - Every ==**Monday**== and ==**Thursday**==

- Deployment cycle will change upon which Org we're working on.
- we have to join the call ==**One-day**== before the deployment cycle to present the changes that what are we've modified.
- Example =: 
			- If Deployment call is on ==**Tuesday**== we've to join the call on ==**Monday**== to present the changes.
			

	-  After all the details are added into the ADO ticket they well verify the ticket and then approve it.
	- They will ==**Provide/Populate**== the [Release date](Release_Date.png)
	-![[Pasted image 20250221142204.png]]
	- In ADO Ticket we need to Mention the ORG name for our reference.
- we need to give the deployment date.
- Example :
		If the deployment tomorrow we need to give tomorrow's date.
- ![[Pasted image 20250221145302.png]]
- After mentioning the Deployment date we've to choose ==**Miscellaneous**==
- After choosing ==(1)== Miscellaneous
- we need to mention QA Passed/Screenshot ==(2)== or Test case in Pre-deployment verification section.
- Then we need to specify that UAT has been Validated and to Confirm we need to send them mail in the UAT Verification ==(3)== section
- ![[Pasted image 20250221150829.png]]

- we can see the Attached mail and QA Screenshots and test cases in the ==Attachments==.
- ![[Pasted image 20250221152543.png]]

## Commit Process

- we need to Provide Commit Id ==(1)== and Build Screenshot ==(2)==
- ![[Pasted image 20250221153703.png]]
- Usually we will be mentioning what are all the components need to be deployed if it
is in minimal.
- else will be Providing separately in Attachments via Excel file. 
- ==Attachments (1)== and ==Deployment Tracker File (2)==
![[Pasted image 20250221154504.png]]
- we need to add all the Changes in what we had in the components in Excel and create a separate sheet.
![[Pasted image 20250221155158.png]]

- Best practice is to add ==Pre-deployment== and ==post-deployment== steps in the **ADO Ticket** 

Example := 
- If we are using **==Custom Settings==** and added records that should be deployed into the prod we need to specify correct ==API name== in the file so that it makes easy for the ==Dev-ops team== to use.


> [!info] ==Organization Wide Email Address==
> we need to create Org wide address in the Prod at least before ==4 days== 

## Why?

- **Basically in Prod org wide Email address will not be available we need to create Org wide address via by requesting ServiceNow ticket to create that org address**
- we **==don't have access==** to Prod to create org wide email address as ==we're not admins== 
- if we don't have **==Org address in Prod==**  or not created in Prod the Commit Will ==FAIL== 
## How to Create ServiceNow Ticket

- **Step 1:** GoTo Grid ==(1)== Icon on top the Screen next to **==CLEAResult==** Via **==Outlook App or From Browser==**
- **Step 2:** Click the ServiceNow ==(2)== Icon 
![[Pasted image 20250221180935.png]]
- After Creating ServiceNow Ticket **==Support Team==** Will create Org wide address in Prod and we need to ask ==**Programming** Team== to Verify the Email.

> [!important] ServiceNow Ticket Creation
> -  Step 3 : HOME ---> Request Something ----> CLEAResult Application Access Request

![[Pasted image 20250221192437.png]]


![[Pasted image 20250221192536.png]]

## How to Create Commit ID ?

- **Step1:** Click to ==REPOS Icon== in the Left Side Bar as Shown in the Below Screenshot

![[Pasted image 20250224144317.png]]

- **Step 2:** Create a ==New Branch==.
	- **Step3**: Each Org have their ==Own Repository==. when we made code changes and planning for Prod Deployment.
	
![[Pasted image 20250224145213.png]]

> [!NOTE] REPOSITORY

>   if we're using APCO-IPL ORG we should **==Create a New Branch==** in that Repository 
 **Step1:** Click New Branch (1)
 **Step2:** Name of the Branch should be the ADO Ticket Number (2) which we created for Deployment and Give meaningful name eg: 1234_CPS_MF  
 
> [!warning] Branch should be created and Always based on the SFDX_UAT Branch
> **Step3:** Always Create Branch Based on SFDX Branch (3)
- ![[Pasted image 20250224151429.png]]

## How to Clone Repository 

 
> [!NOTE] Steps to Clone Repistory

> Step1: Click Branch
> ![[Pasted image 20250224154017.png]]
> Step 2: Click SFDX_ UAT Branch 
> ![[Pasted image 20250224154137.png]]
> Step3: Click the **==Clone==** button
> ![[Pasted image 20250224154316.png]]
> STEP 4: Click **==Clone in VS Code==** and it will create cloned repository in your VS Code
> ![[Pasted image 20250224160559.png]]


> [!NOTE] How to Check the newly created Branch

Step 1: ==CTRL + P button and Click Git Fetch From All Remote==
> +![[Pasted image 20250224161151.png]]
>
You will be seeing the new branch like this 
> ![[Pasted image 20250224161439.png]]
> 
> Click the ==Branch icon== in the VS Code
> ![[Pasted image 20250224161920.png]]
> 
After making changes in the classes which we modified we will be Staging the changes using

![[Pasted image 20250224162236.png]]
> 
Make sure we've given the ADO Ticket Number in the Commit filed and give what you are tyring to commit and then Commit. eg: #1234 added something
>  ![[Pasted image 20250224172611.png]]
>
>And Click Sync changes and Click the Ok Button
>![[Pasted image 20250224172931.png]]
>
>And then Refresh the page branch page in the Web-browser. you will be seeing the changes.
>![[Pasted image 20250224173152.png]]
>
>Create the Pull Request 
>![[Pasted image 20250224173312.png]]
> 
> make sure we targeting the correct branch 
> ![[Pasted image 20250224173527.png]]
> 
> Remove the Description if there are any and if you have any class level change with Test classes add it in the description like comma-separated.
> Click File
> ![[Pasted image 20250224174737.png]]
> 
> if there are any test class present make sure u add it in the description 
> ![[Pasted image 20250224174845.png]]
> ![[Pasted image 20250224174942.png]]
>  
>  There should not be any space after comma separated as shown in the screenshot
>  If there are ==No Test Class== present in your commit leave the description ==blank==  
>  
>  We will be creating the pull Request by clicking ==Create== Button  
>  ![[Pasted image 20250224175321.png]]
>  
>  So, whatever changes we made will be ==validated against the Production== Org  as well the ==Test Code Coverage also==
>  ![[Pasted image 20250224175643.png]]

> [!How It will Check the Code Coverage] 
> Based on the Test Classes we given in the **Description**

> Make sure we are committing to ==SFDX_UAT Branch==  
> ![[Pasted image 20250224180604.png]]
> 
> And GoTo SFDX_UAT Branch and Click the Commits.
> 
> ![[Pasted image 20250224180736.png]]

> [!How to Copy Commit ID]
>Just copy the link as shown in the screenshort

![[Pasted image 20250224181050.png]]

## Summary 

- We need to ==create an ADO Ticket== and in the Release note we need to mention the commit ID and what are all the changes and classes level or in created custom label also.
- we should ==clone== the repository in to our VS Code and make the changes and then commit
- We Should give the Description if we have any classes level changes in by comma-separated
- ==Test Class Code Coverage== will be Validated in prod also based on the ==Description== given while validating against the Prod Org