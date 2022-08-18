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
- From within EC2 navigate to Launch Instance


- Next you will be asked to select the machine you wish to use or the OS


- Then you will be asked to select an instance type


- Next you will need to input some configuration details specific to your needs


- Select the type and amount of storage you will require


- Create the relevant tags 


- Configure your security group to allow the neccesary ports


- Review all you have done and make changes accordingly



- Be sure to select the correct key when prompted



- Once your instance is up and running you can check this from within the EC2 interface


- Once you have selected your instance up at the top left you can select connect

- From within this tab go into the ssh tab and you will be able to find your ssh path you will need to access this VM from your localhost terminal


- Navigate to the .ssh folder where your key is stored


- Run the copied link from EC2, follow any prompts answering yes etc


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






