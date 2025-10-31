# Set up AWS EC2 Instance to automatically start and stop at a specific point in time.

## Full Step-by-Step guide with snapshots to describe and illustrate how an AWS EC2 Instance can start and stop at custom times

### This project demonstrates how one can both test the stopping and starting of an EC2 Instance as well as scheduling both a customized stop and start time for an EC2 Instance. In this project, we will be covering how to:
*Create an EC2 Instance 
* Create a Lambda Function for both stopping and starting the created EC2 Instance
*  Set up the appropriate policies to test both the stopping and starting of an EC2 Instance.
*  Create a CloudWatch schedule to both stop and start the EC2 Instance automatically at Custom Times.



#### Step-by-Step Instructions on how to set up customizable times to both Start and Stop an EC2 Instance:



---

# **EC2 Instance Setup**

**Select EC2 from AWS Searchbox and Select EC2 Pop up option**

<p align="center">  
  <img src="resources/EC2searchec2andselect.png" alt="Select Instance from AWS left-hand menu" width="900" />  
</p>  

**Select the Launch Instance tab**

<p align="center">  
  <img src="resources/EC2LAUNCHINSTANCETABINITIAL.png" alt="Click Launch Instance tab" width="900" />  
</p>  

**Give your instance a name & select an AMI for the instance** 
<p align="center">  
  <img src="resources/EC2INSTANCELAUNCHINSTANCE NAMEANDAMI.png" alt="Enter instance name & select AMI for the Instance" width="900" />  
</p>  


**Select the instance type & Select the key pair**

<p align="center">  
  <img src="resources/EC2INSTANCELAUNCHINSTANCESETUPINSTANCETYPEANDKEYPAIR.png" alt="Choose instance type & Select Keypair" width="900" />  
</p>  





**Click Launch Instance at the bottom**

<p align="center">  
  <img src="resources/EC2INSTANCELAUNCHINSTANCESELECTLAUNCHINSTANCEBUTTON.png" alt="Launch EC2 instance confirmation buttoN" width="900" />  
</p>  

---

# **Policies**

**Search IAM and open Policies**

<p align="center">  
  <img src="resources/CREATEPOLICYSelectIAMsearchbox.png" alt="Search IAM and select Policies" width="900" />  
</p>  

**Click Create Policy**

<p align="center">  
  <img src="resources/CREATEPOLICYSelectCreatePolicybuttonend.png" alt="Create new IAM policy" width="900" />  
</p>  

**Select the JSON tab**

<p align="center">  
  <img src="resources/CREATEPOLICYSelectJSONtab.png" alt="Select JSON tab in policy editor" width="900" />  
</p>  

**Insert custom policy code**

<p align="center">  
  <img src="resources/CREATEPOLICYActualPolicy.png" alt="Insert custom JSON policy code" width="900" />  
</p>  

**Click Next**

<p align="center">  
  <img src="resources/CREATEROLEClickNextafterselectingpreviouspolicy.png" alt="Click Next to continue policy creation" width="900" />  
</p>  

**Create a name for your policy**

<p align="center">  
  <img src="resources/CREATEPOLICYGiveNametoPolicy.png" alt="Name the IAM policy" width="900" />  
</p>  

**Click Create Policy**

<p align="center">  
  <img src="resources/CREATEPOLICYSelectCreatePolicybuttonend.png" alt="Click Create Policy button" width="900" />  
</p>  

**Open Roles from the sidebar**

<p align="center">  
  <img src="resources/CREATEROLESSelectRolesFromOptions.png" alt="Select Roles from left-hand options" width="900" />  
</p>  

**Click Create Role**

<p align="center">  
  <img src="resources/CREATEROLEClickCreateRoleend.png" alt="Create new IAM role" width="900" />  
</p>  

**Select Lambda as the service or use case**

<p align="center">  
  <img src="resources/CREATEROLESSelectLamdaasusecase.png" alt="Select Lambda as the service use case" width="900" />  
</p>  

**Attach the previously created policy**

<p align="center">  
  <img src="resources/CREATEROLESSearchforpreviouslycreatedpolicy.png" alt="Attach existing IAM policy to role" width="900" />  
</p>  

**Click Next**

<p align="center">  
  <img src="resources/CREATEROLEClickNextafterselectingpreviouspolicy.png" alt="Click Next during role creation" width="900" />  
</p>  

**Give your role a name**

<p align="center">  
  <img src="resources/CREATEROLEGiveyourRoleaname.png" alt="Enter IAM role name" width="900" />  
</p>  

**Click Create Role**

<p align="center">  
  <img src="resources/CREATEROLEClickCreateRoleend.png" alt="Confirm Create Role" width="900" />  
</p>  

---

# **Lambda — Test Instance Start/Stop**

**Open Lambda from the AWS search bar**

<p align="center">  
  <img src="resources/LAMBDASelectLambdaAWSSearchbox.png" alt="Search and open Lambda service" width="900" />  
</p>  

**Click Create Function**

<p align="center">  
  <img src="resources/LAMBDACreateFunctionbuttonintial.png" alt="Click Create Function in Lambda" width="900" />  
</p>  

**Enter function name**

<p align="center">  
  <img src="resources/LAMBDAGiveFunctioName.png" alt="Enter Lambda function name" width="900" />  
</p>  

**Select Python 3.9 as runtime**

<p align="center">  
  <img src="resources/LAMBDASelectRuntime.png" alt="Select Python 3.9 as runtime" width="900" />  
</p>  

**Use an existing role**

<p align="center">  
  <img src="resources/LAMBDAExecutionroleSelectOption.png" alt="Select Use an existing role option" width="900" />  
</p>  

**Select the role created earlier**

<p align="center">  
  <img src="resources/LAMBDASelectExistingRoleDropdown.png" alt="Select the previously created IAM role" width="900" />  
</p>  

**Click Create Function at the bottom**

<p align="center">  
  <img src="resources/LAMBDACreateFunctionbuttonEND.png" alt="Create Lambda function" width="900" />  
</p>  

**Copy EC2 Instance ID from the instance details**

<p align="center">  
  <img src="resources/LAMBDASelectInstanceID.png" alt="Copy EC2 instance ID" width="900" />  
</p>  

**Add Lambda function code for stop instance and insert instance ID**

<p align="center">  
  <img src="resources/LAMBDASTOPINSTANCEPYTHONCODE.png" alt="Add Lambda code with EC2 instance ID" width="900" />  
</p>  

**Create and run a new test**

<p align="center">  
  <img src="resources/LAMBDASelectTestButton.png" alt="Create and execute Lambda test" width="900" />  
</p>  

**Deploy the function code**

<p align="center">  
  <img src="resources/LAMBDAClickDeploy.png" alt="Deploy Lambda function" width="900" />  
</p>  

**Open Functions**

<p align="center">  
  <img src="resources/LAMBDAClickFunctionsoptions.png" alt="Select Lambda function" width="900" />  
</p>  

 **Select the created function**
<p align="center">  
  <img src="resources/LAMBDASelectFunction.png" alt="Select Lambda function" width="900" />  
</p>  

**Test the function from the Actions dropdown**

<p align="center">  
  <img src="resources/LAMBDASelectActionsbutton.png" alt="Test Lambda from Actions dropdown" width="900" />  
</p>  


**Click Test**

<p align="center">  
  <img src="resources/LAMBDAClickTest.png" alt="Test Lambda from Actions dropdown" width="900" />  
</p>  



**Check EC2 instance shows 'Stopping'**

<p align="center">  
  <img src="resources/LAMBDATESTstoppingofEC2Instance REVISED.png" alt="Confirm EC2 instance stopping state" width="900" />  
</p>  

**Repeat steps with modified code to start instance**

<p align="center">  
  <img src="resources/LAMBDA_START_FUNCTION_CODE.png" alt="Lambda function code for starting EC2 instance" width="900" />  
</p>  

---

# **Create CloudWatch Schedule (Stop Instance Automatically)**

**Search CloudWatch and open it**

<p align="center">  
  <img src="resources/SCHEDULESelectCloudwatchAWSSearch.png" alt="Search and open CloudWatch" width="900" />  
</p>  

**Select View Events**

<p align="center">  
  <img src="resources/SCHEDULESelectviewevent.png" alt="View events in CloudWatch" width="900" />  
</p>  

**Click Create Rule**

<p align="center">  
  <img src="resources/SCHEDULESelectCreateRule.png" alt="Create new CloudWatch rule" width="900" />  
</p>  

**Name the rule and select Schedule type**

<p align="center">  
  <img src="resources/SCHEDULESGiveRuleaName.png" alt="Name and choose Schedule rule type" width="900" />  
</p>  

<p align="center">  
  <img src="resources/SCHEDULESelectScheduledialogbox.png" alt="Name and choose Schedule rule type" width="900" />  
</p> 

**Click Continue to Create Rule**  

<p align="center">  
  <img src="resources/SCHEDULESelectContinuetoCreateRule.png" alt="Set custom time for instance stop" width="900" />  
</p>  

**Set custom schedule time**
<p align="center">  
  <img src="resources/SCHEDULESettimesStopInstances.png" alt="Set custom time for instance stop" width="900" />  
</p>  




**Choose Lambda function as target**

<p align="center">  
  <img src="resources/SCHEDULESelectaTargetforRule.png" alt="Select Lambda function as CloudWatch target" width="900" />  
</p>  

**Select stop function and create rule**

<p align="center">  
  <img src="resources/SCHEDULESelectafunctionForRule.png" alt="Select stop instance Lambda function" width="900" />  
</p>  

**Verify EC2 instance stops at scheduled time**

<p align="center">  
  <img src="resources/SCHEDULESINSTANCEACTUALLYSTOPPING.png" alt="EC2 instance stopped automatically" width="900" />  
</p>  

---

# **Create CloudWatch Schedule (Start Instance Automatically)**

**Repeat steps from stop schedule setup, except for using a different rule name and selecting the start function**




<p align="center">  
  <img src="resources/CLOUDWATCH_SELECT_START_FUNCTION.png" alt="Select start instance Lambda function" width="900" />  
</p>  


<p align="center">  
  <img src="resources/SCHEDULESelectafunctionForRuleSECONDFUNCTION.png" alt="Select start instance Lambda function" width="900" />  
</p>  






  
  

  


 














##### Contribution Policy

This project is not accepting external contributions, including pull requests or feature requests.

It serves as a personal archive of my learning journey in applying foundational concepts in software development and version control. Active development is not ongoing, and external changes will not be integrated.

Thank you for your understanding.
