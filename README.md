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

As for the Network settings portion of the EC2 configuration, you need first to review the Network VPC and Subnet selections, and lastly your pubic IP

<img width="865" height="286" alt="image" src="https://github.com/user-attachments/assets/97168e59-f1fd-4919-a059-821a7333d079" />

