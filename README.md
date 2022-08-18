# CLOUD COMPUTING


![Blank diagram (3)](https://user-images.githubusercontent.com/110179866/185412518-d35eacf2-1c73-4f85-b971-82ad50675091.jpeg)





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






