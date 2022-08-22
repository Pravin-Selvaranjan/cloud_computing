# CLOUD COMPUTING


![Blank diagram (4)](https://user-images.githubusercontent.com/110179866/185669444-81d1ba74-2acd-4eec-be7d-ab483831ba4e.jpeg)





Purchasing a laptop

- OS windows10/11(pro/home) - ubuntu 16.04 lts - vagrant
- PROCESS POWER
- RAM
- SSD - storage - volume - persistent data - y/n - eg USB drive
- HARD DRIVE
- GRAPHICS CARD
- POWER SUPPLY
- GOOD QUALITY
- CPU
- MOTHERBOARD
- TOUCH SCREEN 
- upgrading ram? to increase performance
- Firewall - Security tool
  

## Purpose?

- Personal use
- official use
- gaming


## AWS IAM login 
### Best practices
- Naming convention - eng122_pravin_ec2
- AWS Services to be used  between 0900-1800 stop or terminate
- If you need to use it out of hours please ask
- We must only use IRELAND
- Terminate services once you finished working with them
- Do not delete anyone else's services
- MUST NOT SHARE AWS account details or keys with anyone - or push to github


AWS - PROVIDE GLOBAL ADDRESS IP WE NEED TO BUILD CUSTOMISED FIREWALL FOR PORT 3000-80-27017
ETC

nginx installed visible on the global IP

ec2 to allow accvess to our localhost to ssh in by default port 22

app code - app folder
with nodejs
dependencies required (nginx,nodejs)


# Where do we begin on AWS?
## Creating a VM utilising EC2 instances 
- Once logged in go to EC2


<img width="956" alt="ec2" src="https://user-images.githubusercontent.com/110179866/185447699-e3f55ed4-7714-4bbd-89a4-a9a089e99ca5.png">



- From within EC2 navigate to Launch Instance

<img width="434" alt="launch instance" src="https://user-images.githubusercontent.com/110179866/185447725-001fb9af-4ce6-4b2b-a53f-15a1e7de5a4b.png">


- Next you will be asked to select the machine you wish to use or the OS


<img width="952" alt="select a machine" src="https://user-images.githubusercontent.com/110179866/185447745-07e9299a-e2eb-4a0a-9f56-77cca5b4e07c.png">


- Then you will be asked to select an instance type



<img width="961" alt="instance type" src="https://user-images.githubusercontent.com/110179866/185447777-993baeed-70cc-49ec-b9c6-f0a826ef5b54.png">


- Next you will need to input some configuration details specific to your needs



<img width="956" alt="config inst details" src="https://user-images.githubusercontent.com/110179866/185447801-4d825e1a-0953-4578-9991-1076d76e6291.png">


- Select the type and amount of storage you will require



<img width="962" alt="storage" src="https://user-images.githubusercontent.com/110179866/185447829-4ad5b405-3b7b-422d-ab2c-413725adee4f.png">


- Create the relevant tags 


<img width="957" alt="tags" src="https://user-images.githubusercontent.com/110179866/185447846-26285fb0-fbae-4784-9083-a99e4dff60dc.png">



- Configure your security group to allow the neccesary ports



<img width="956" alt="sg" src="https://user-images.githubusercontent.com/110179866/185447863-d75d7d67-f203-4aeb-b966-af06de93980d.png">



- Review all you have done and make changes accordingly



<img width="953" alt="review" src="https://user-images.githubusercontent.com/110179866/185447889-92f43dad-7248-4ad7-89bf-87b9ee747916.png">



- Be sure to select the correct key when prompted



- Once your instance is up and running you can check this from within the EC2 interface



<img width="956" alt="instances running" src="https://user-images.githubusercontent.com/110179866/185447925-94809ef0-76c9-4e86-a1fa-ac1ebfdcbb7a.png">


- Once you have selected your instance up at the top left you can select connect


- From within this tab go into the ssh tab and you will be able to find your ssh path you will need to access this VM from your localhost terminal


<img width="959" alt="connect ssh" src="https://user-images.githubusercontent.com/110179866/185447984-f511f00e-8cd8-4b61-9839-842362cfb45c.png">


<img width="398" alt="ssh link" src="https://user-images.githubusercontent.com/110179866/185448082-65d28411-b381-49e1-beb6-8095a4254679.png">



- Navigate to the .ssh folder where your key is stored

<img width="449" alt="LOCAL SSH" src="https://user-images.githubusercontent.com/110179866/185448212-113bdac2-da17-45f7-85fd-8c8f463175fa.png">

- Run the copied link from EC2, follow any prompts answering yes etc





<img width="447" alt="public link" src="https://user-images.githubusercontent.com/110179866/185448285-43e1884b-b633-402a-bd2e-8f991c9f769f.png">



- Once you are within the VM be sure to run update and upgrade commands `sudo apt-get update -y` `sudo apt-get upgrade -y`


- We can also now install any dependencies such as Nginx using `sudo apt install nginx` and nodejs


- Ensure to run upgrade and update commands


## VM is set up

- Now we need to migrate any folders containing data required to run the application from our localhost to the EC2 instance


- We use the scp method (Secure copy) 

- Using the following command we can transfer file/files to our EC2 instance (replace the relevant file paths with your own)

```scp  -i ~/.ssh/eng122.pem -r Deployment_eng122 ssh  ubuntu@ec2-52-49-177-104.eu-west-1.compute.amazonaws.com:```

- You may receive errors and this is usually down to the file path being incorrect 


- If successful this process can take up to 10 minutes dependent on how much data is contained within your folder


- Once this process has completed within your VM use `ls` to confirm that the items have successfull migrated

- You can then go ahead and install any further required dependencies such as `npm` etc 

- Once you have run and upgraded/updated, navigate to the correct folder 

- In my case this is `cd app`

- From here we can run `npm start` and our app should be live 






# What is Cloud Computing? 

- Servers, databases, networks, storage drives, and the list go on. All of these things are now deliverable and usable over the internet and have been for some time. We typically pay for only the specific services we use, resulting in a very cost-effective formula. 


- On-demand
 On-demand self service resource sourcing is a prime feature of most cloud offerings where the user can scale the required infrastructure up to a substantial level without disrupting the service

- Elastic rapid provision and release
Rapid elasticity allows users to automatically request additional space in the cloud or other types of services. Because of the setup of cloud computing services, provisioning can be seamless for the user


- Metered service
The user or customer has access to an incredible amount of resources but only pays for what they actually use. 
It is estimated that by 2025, over 100 zettabytes of data will be stored in the cloud. By comparison only 25% of all computing data was stored this way just 7 years ago in 2015. This is a mammoth statistic and demonstrates the rapid expansiveness of the cloud.


# Benefits of Cloud Computing?

- Lower costs - Cloud computing is more cost effective than traditional IT infrastructure due to methods of payment for the data storage services. With cloud based services, you only pay for what is used – similarly to how you pay for utilities such as electricity. Furthermore, the decreased likelihood of downtime means improved workplace performance and increased profits in the long run.

- Collaboration - Cloud environments enables better collaboration across teams: developers, QA, operations, security and product architects are all exposed to the same infrastructure and can operate simultaniously without stepping on each other toes. Cloud roles and permissions help with better visibility and monitoring on who did what and when, to avoid conflicts and confusion. Different cloud environments can be built for specific purposes like staging, QA, demo or pre-production. It’s much easier to collaborate in a transparent manner and the cloud encourages it.


- Agile and Adaptable - Cloud computing services are great for businesses whose demands constantly grow or fluctuate. Whether you require more bandwidth or want to reduce capacity, your cloud service provider can adapt to your demands, so you’ll never have to pay for expensive upgrades. This can give you a real competitive edge because you get to retain total control and freedom over your IT infrastructure.  



# Types of Cloud Computing

- IaaS - Cloud infrastructure services, known as Infrastructure as a Service (IaaS), are made of highly scalable and automated compute resources. IaaS is fully self-service for accessing and monitoring computers, networking, storage, and other services. IaaS allows businesses to purchase resources on-demand and as-needed instead of having to buy hardware outright.


- PaaS - Cloud platform services, also known as Platform as a Service (PaaS), provide cloud components to certain software while being used mainly for applications. PaaS delivers a framework for developers that they can build upon and use to create customized applications. All servers, storage, and networking can be managed by the enterprise or a third-party provider while the developers can maintain management of the applications.



- SaaS - Software as a Service, also known as cloud application services, represents the most commonly utilized option for businesses in the cloud market. SaaS utilizes the internet to deliver applications, which are managed by a third-party vendor, to its users. A majority of SaaS applications run directly through your web browser, which means they do not require any downloads or installations on the client side.


- IaaS  - Key advantages are , Most flexible cloud computing model, making it easier to automate deployment of storage networking servers and processing power and its highly scalable. An example of IaaS would be AWS. 

- SaaS – Key advantages  SaaS provides numerous advantages to employees and companies by greatly reducing the time and money spent on tedious tasks such as installing, managing, and upgrading software. This frees up plenty of time for technical staff to spend on more pressing matters and issues within the organization. An example of this would be something like Gmail

- PaaS – Key advantages – Simple and cost effective, Highly available and significantly reduces the amount of required coding. An example of this would be something like Elastic Beanstalk. Elastic Beanstalk is a platform within AWS that is used for deploying and scaling web applications. In simple terms this platform as a service (PaaS) takes your application code and deploys it while provisioning the supporting architecture and compute resources required for your code to run.



# Pro's and Con's

### Advantages 
-  No cost on infrastructure - In all types of Cloud computing (SaaS etc), one thing is common in that you don’t need to invest in hardware or any infrastructure. In general, every organization has to spend a lot on their IT infrastructure to set up and hire a specialized team.

- Accessibility and pay per use - Cloud resources are easily accessible from around the globe – anytime, anywhere and from any device and you have complete access to your resources.
This decides your billing also -you only pay for what you use and how much you use. It’s like your phone or electricity bill. But with other IT infrastructure, one spends the complete amount in one go and it is very very rare that those resources are used optimally and thus, the investment goes waste.

### Disadvantages

- Strong internet - To access your cloud services, you need to have a good internet connection always with good bandwidth to upload or download files to/from the cloud


- Security - Security of data is a big concern for everyone. Since the public cloud utilizes the internet, your data may become vulnerable.


- Vendor Lock-in- Although the cloud service providers assure you that they will allow you to switch or migrate to any other service provider whenever you want, it is a very difficult process.


# AWS Global Infrastructure


### The AWS Global Cloud infrastructure is the backbone network of global data centres and other platforms that Amazon uses to deliver application workloads and AWS services.

### For cloud application and service delivery, customers provision and connect their end users and organizational environments to the following AWS global infrastructure components:


-	AWS Regions - AWS Regions are physical locations around the world where Amazon clusters data centres for application and service delivery in AWS Availability Zones. 

-	AWS Availability Zones - An Availability Zone (AZ) is a grouping of one or more discrete data centers that provide applications and services in an AWS region.

-	AWS Local Zones - AWS Local Zones are provisioned to run high-speed applications—such as media, entertainment, real-time gaming, live video streaming, and machine learning—that require single-digit millisecond latency to service users in specific geographic locations.

-	AWS Wavelength Zones - Wavelength zones provide 5G telecommunications connections inside AWS Regions.

### The AWS cloud spans 84 Availability Zones within 26 worldwide geographic regions. Announced plans include 21 more Availability Zones and seven more regions in Europe, Asia, and Australia.
There are currently e17 AWS Local Zones for ultralow latency applications.
There are 28 Wavelength Zones available for ultralow latency and 5G processing.





# User data instance on EC2

## We can automate the installation and updates of our VM by using user data within EC2

- Once we are at Step 3 of the above instance creation steps if we scroll down we can see advanced settings

- Once in advanced settings we can go to the user data text box and input a list of instructions utilising the following command `#!/bin/bash` to initialise the script

- Then we continue on and select the other relevant settings and launch our instance, this may take longer than usual considering we are installing as we up the instance

