# AWS-EC2-LAUNCH
Steps to launch an EC2 instance with a Linux OS in AWS

First, log in to your management console and search for EC2 in the search bar

<img width="956" height="1080" alt="image" src="https://github.com/user-attachments/assets/65ad9ec3-475f-4ca1-9310-d5b11c37fcc7" />

In the left navigation pane, under the Instances drop-down, select instances

<img width="957" height="1075" alt="image" src="https://github.com/user-attachments/assets/5f22f1a2-c304-4ef4-8d65-802e11bf045b" />

Once the page has load you should then right click the Launch instances tab in orange

<img width="957" height="1077" alt="image" src="https://github.com/user-attachments/assets/6ac81794-a104-4fb1-b081-1c10e6736868" />

Once the Launch Instances page has loaded, you can now begin the configuration processes for the EC2 

<img width="1917" height="1080" alt="image" src="https://github.com/user-attachments/assets/fd404fcc-2fc9-4f02-ba18-f808ce3fe907" />

First, you must enter a name for your instance, such as My First EC2. Optionally, you can add tags to help organize and identify your resources

<img width="879" height="219" alt="image" src="https://github.com/user-attachments/assets/fce6b178-8eca-4a29-9129-2fec85a57bf6" />

Next, you must choose an Amazon Machine Image (AMI).  An AMI is a template that contains the operating system and other software used to launch your instance

You can search through the catalog of applications and OS images, but I will be using the Quick Start section, where I will choose Amazon Linux provided by AWS

<img width="868" height="440" alt="image" src="https://github.com/user-attachments/assets/248bcbc5-8914-40e1-bf3f-606e8569064b" />

Next, verify the selected AMI and its eligibility for any applicable Free Tier benefits

<img width="835" height="287" alt="image" src="https://github.com/user-attachments/assets/eb328fdc-d5f5-4252-a600-82ba9b044d39" />

Then, under Architecture, choose the processor architecture supported by your selected AMI

<img width="858" height="206" alt="image" src="https://github.com/user-attachments/assets/05cb2bd0-657b-4f59-97ce-668f87ce210c" />

Navigate down the page to the Instance type section. Here, you can choose from various configurations that differ in processing power (CPUs), storage capacity, and pricing

<img width="878" height="577" alt="image" src="https://github.com/user-attachments/assets/1780f023-d8dd-414f-b4d1-66dce76fa112" />

Then you will need to create a new key pair to connect to your instance securely. However, you can proceed without one

<img width="1024" height="353" alt="image" src="https://github.com/user-attachments/assets/b04ef666-4386-4fe3-b990-f8b74ce1d15e" />

Moving on with the creation, select Create new key pair, circled in red in the image above

<img width="959" height="1079" alt="image" src="https://github.com/user-attachments/assets/4fd845ca-9adb-4c05-b49f-c0ddf918c5c0" />

Then, when prompted, enter a name for the key pair, such as EC2 Tutorial

<img width="747" height="190" alt="image" src="https://github.com/user-attachments/assets/1b789ffd-0ec9-45c2-946a-43ab9ef97d37" />

You can then choose between two key pair types: RSA or ED25519

<img width="715" height="124" alt="image" src="https://github.com/user-attachments/assets/e1f0d6c8-b026-45e3-b5f5-4f091d13b771" />

Select the private key file format that matches your operating system. Choose the .pem format if you are using macOS, Linux, or Windows 10 and newer, as it provides broad compatibility across modern systems. 

Alternatively, select the .ppk format if you are using older Windows environments, such as Windows 7 or 8, which require PuTTY for SSH connections. Once you have made your selection, click Create key pair to generate and save your credentials

<img width="754" height="365" alt="image" src="https://github.com/user-attachments/assets/3744d13d-3104-4e4b-9450-243ad73d37c1" />

<img width="549" height="235" alt="image" src="https://github.com/user-attachments/assets/a7e9994c-aed7-47db-beb3-50bea3980320" />

When you create an EC2 key pair, the downloaded file is your private key file (saved with either a .pem or .ppk extension, depending on the format you selected), as seen in the image above

As for the Network settings portion of the EC2 configuration, you need first to review the Network VPC, Subnet selections, and lastly your pubic IP

<img width="865" height="286" alt="image" src="https://github.com/user-attachments/assets/97168e59-f1fd-4919-a059-821a7333d079" />

The first security group created will be called "launch-wizard-1". You also need to configure the Firewall in the Network settings by adding rules that will control traffic to and from our instance. The first rule that will need to be set is to allow SSH traffic from anywhere

<img width="858" height="231" alt="image" src="https://github.com/user-attachments/assets/220dea9f-fe6e-4ac9-9468-eaed5444eb4a" />

Then we also want to allow HTTP traffic from the internet. This is necessary because we will be launching a web server on our EC2 instance. Check the box and continue to the Configure storage section

<img width="958" height="1080" alt="image" src="https://github.com/user-attachments/assets/f9d49fa2-9855-499f-815f-7e126ecabf8c" />

In Configure storage, we will leave the settings as is: 8 GiB gp3 Root volume, 3000 Input/Output Operations Per Second (IOPS), and we can leave File systems selection on none

<img width="877" height="265" alt="image" src="https://github.com/user-attachments/assets/71a5791a-11de-48f6-a2ae-da42f4a9c0c6" />

Moving on, under Advanced details we are going to skip down the page until you see User data. 

<img width="928" height="767" alt="image" src="https://github.com/user-attachments/assets/5aa6eb7f-ed21-42bb-9871-3b1ab0976809" />

User data is a script or set of commands that runs automatically on your instance when it boots up for the first time

<img width="925" height="766" alt="image" src="https://github.com/user-attachments/assets/76087854-2b9b-4e1b-aecb-2ae2dbb20b30" />

This script performs system updates, installs and starts the Apache HTTPD server, configures it to launch automatically on boot, and creates a basic 'Hello World' web page

Finally, we have the Summary section, which is a review of everything you configured above. once you have reviewed the information you can Launch the instance

<img width="963" height="1080" alt="image" src="https://github.com/user-attachments/assets/7cf49e49-4ef3-41ff-b5c3-e68afbc4825c" />

You should receive the banner indicating that your instance was successfully launched

<img width="961" height="1080" alt="image" src="https://github.com/user-attachments/assets/b245e012-2767-42d4-b236-b83256672a07" />

To confirm this, you can toggle back over to the left navigation pane and right-click instances

Here you can see the EC2; "My First EC2" was launched, and the instance state is now Running

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/380581d3-30a1-44b3-8cc2-481b8edc9f6f" />

When you click on the newly created instance, you can view more information about the EC2 instance in the Details tab

In this tab, you can find the instance ID, the public IPv4 address, which will be used to access our EC2 instance, and the private IPv4 address, which is used to gain access internally on the AWS network privately

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c2382ffe-ee54-4b6f-9c6f-32d3e70412d7" />

Scrolling down reveals additional details, including the hostname, private DNS, instance type, AMI in use, and associated key pair, as seen in the screenshots below:

<img width="1920" height="501" alt="image" src="https://github.com/user-attachments/assets/049688f2-6999-43c5-8e8a-6a203cbc6502" />

<img width="1917" height="507" alt="image" src="https://github.com/user-attachments/assets/fa93d6a7-fe9f-4109-9f78-54ec6804a920" />

<img width="589" height="439" alt="image" src="https://github.com/user-attachments/assets/120f2e0b-1281-4388-9391-9a75b2bc3579" />

Moving on, we also have the Security tab that holds info on the security group that was created named launch wizard 1

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/0f76dace-b42e-4f3c-bd48-b59f3bbd59d1" />

Security tab also displays the inbounds rules:

Inbound security rules permit traffic on ports 22 (SSH) and 80 (HTTP) from the 0.0.0.0/0 (anywhere) source IP

<img width="1598" height="281" alt="image" src="https://github.com/user-attachments/assets/9ee86a63-1869-4def-912b-3707c0d6a8af" />

The outbound rule is set to the default configuration, permitting all outbound traffic from the instance to any IPv4 address:

<img width="1555" height="251" alt="image" src="https://github.com/user-attachments/assets/ff78c013-70a1-4d17-936e-7ecef21d73d2" />

The following image displays the instance's storage configuration under the Storage tab

<img width="1917" height="510" alt="image" src="https://github.com/user-attachments/assets/cca9df74-bb36-4048-affa-387e9ca4488d" />

The instance has a single 8 GiB storage volume attached, mounted at /dev/xvda and currently in use

<img width="1592" height="250" alt="image" src="https://github.com/user-attachments/assets/1a76be13-0911-4268-9092-5b1b3b812ba2" />

After reviewing the details, security, and storage tabs, we can now open the web server running on the instance

You want to navigate back to the Details tab and copy the Public IPv4 address and simply paste it into the address bar of a new web browser as demonstrated in the screenshots below

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b6cfc826-02e9-4009-b3aa-8fceedef50c3" />

<img width="1920" height="442" alt="image" src="https://github.com/user-attachments/assets/db0a5d08-d4b7-421e-9cfa-977dc0689b68" />

However, if you have trouble accessing the server, make sure to input http:// before the address

<img width="963" height="1080" alt="image" src="https://github.com/user-attachments/assets/c3479537-9bd6-48bc-bd1f-f23796b0a7b2" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/af7faae7-7f5d-4a8a-a131-be25429ec8f5" />

What should be displayed when opened is the Hello World message that was entered into the user data box earlier, along with the  Private IPv4 address

<img width="207" height="56" alt="image" src="https://github.com/user-attachments/assets/89899e2f-7845-4cfe-8fcc-8719892dbee3" />

