# Set up AWS EC2 Instance to automatically start and stop at a specific point in time.

## Full Step-by-Step guide with snapshots to describe and illustrate how an AWS EC2 Instance can start and stop at custom times

### This project demonstrates how one can customize the timings of their choice to both start and stop an EC2 Instance.  In this project, we will be covering how to:

* Create a Custom Policy in order.......



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




LAMBDA

* Select Lambda after typing it in AWS Searchbox

* Select Create Function

* Give Your Function a name in the Function Name Box

*Select Python 3.9 from the Runtime Dropdown box

* Select Use an Existing Role from the Execution Role options

* Select the role that you created earlier from the Existing Role Dropdown box.

* Select Create Function at the bottom.


* Go back to the EC2 Instance Created Earlier and Copy the Instance ID 


*  Scroll Down to Code Source and type the code (as I illustrated below). REMEMBER TO INSERT YOUR INSTANCE ID THAT WAS COPIED FROM EARLIER. (CIRCLED.)


 














##### Contribution Policy

This project is not accepting external contributions, including pull requests or feature requests.

It serves as a personal archive of my learning journey in applying foundational concepts in software development and version control. Active development is not ongoing, and external changes will not be integrated.

Thank you for your understanding.
