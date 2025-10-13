# Set up AWS EC2 Instance to automatically start and stop at a specific point in time.

## Full Step-by-Step guide with snapshots to describe and illustrate how an AWS EC2 Instance can start and stop at custom times

### This project demonstrates how one can both test both the stopping and starting of an EC2 Instance as well as scheduling both a customized stop and start time for an EC2 Instance. In this project, we will be covering how to:

* Create a Lambda Function in order to test both the stopping and starting of an EC2 Instance.



#### Step-by-Step Instructions on how to set up customizable times to both Start and Stop an EC2 Instance:
EC2 INSTANCE SETUP

* Select Instance from Left-Handed-Options

* Select the LaunchInstance tab

* Give Your Instance a Name

* Select an AMI for the Instance

* Select the Instance Type for the Instance

* Select the keypair to be used for the Instance

* Select Launch Instance at the bottom



POLICIES
* Search IAM from AWS Searchbox and then select Policies from the options.

* Click Create Policy

* Select JSON Tab

* Insert Custom Policy into the Policy Editor (as I illustrated below.)

*Click Next


* Create a Name for your Policy.


* Click Create Policy at the bottom.


* Select Roles from left-handed-options.


* Select Create Role


* Select Lambda from Service or Use Case Dropdown Box.

* Select the policy that you previously created from the search box and drop-down options.


* Select Next at the bottom.


* Give your Role a Name


* Select Create Role at the bottom.




LAMBDA TEST THE INSTANCE BOTH STARTING AND STOPPING

* Select Lambda after typing it in AWS Searchbox

* Select Create Function

* Give Your Function a name in the Function Name Box

*Select Python 3.9 from the Runtime Dropdown box

* Select Use an Existing Role from the Execution Role options

* Select the role that you created earlier from the Existing Role Dropdown box.

* Select Create Function at the bottom.


* Go back to the EC2 Instance Created Earlier and Copy the Instance ID 


*  Scroll Down to Code Source and type the code (as I illustrated below). REMEMBER TO INSERT YOUR INSTANCE ID THAT WAS COPIED FROM EARLIER .

* Click Test Button from the left side of the code source. Followed by Creating a New test> Give Your New Test and Select Save.

* Click Deploy in order to deploy the Python Code that was written(as illustrated above)

* Click Functions from Left-Handed-Options

* Select the Function that was Created

* Select the Test from the Actions Dropdown list

* Go back to your Created Instance, Refresh the Instance and confirm that it says Stopping under Instance State.

* REPEAT ALL THE STEPS RELATED TO LAMBDA FROM ABOVE. HOWEVER USE THE MODIFIED CODE IN CODE SOURCE(Illustrated Below.)


CREATE A CLOUDWATCH SCHEDULE TO STOP THE INSTANCE AT A CUSTOM TIME AUTOMATICALLY :

* Search for Cloudwatch from the AWS Searchbox & Select it.

* Select View Events on the Cloudwatch Page

* Select Create Rule

* Give your rule a name

*Switch the Rule Type to Schedule

* On the bottom, Select Continue to Create Rule

* In the schedule pattern dialog box, set the time for the instance to stop automatically at your desired future time (using the format shown in the image below).

* Click Next at the bottom of the page.

* In the Select a Target dropdown box, select Lambda Function

* In the function dropdown box, select stop instance(created earlier when creating the Lambda Functions.)

* Click Next at the bottom of the page.

* Skip the tags page and go to the bottom of the Review and Create Page and select Create Rule.

* Go back to the EC2 Instance and see that it has stopped at the time that was specified earlier. (Click Refresh a few times if the Instance does not stop.)

CREATE A CLOUDWATCH SCHEDULE TO START THE INSTANCE AT A CUSTOM TIME AUTOMATICALLY:

* Repeat all the steps related to "Create a Cloudwatch Schedule to Stop the Instance at a Custom Time Automatically" with two exceptions:

* 1) Give a different name for the rule
  2) Select "startfunction" under the function dropdown box.



  
  

  


 














##### Contribution Policy

This project is not accepting external contributions, including pull requests or feature requests.

It serves as a personal archive of my learning journey in applying foundational concepts in software development and version control. Active development is not ongoing, and external changes will not be integrated.

Thank you for your understanding.
