
# User data instance on EC2

## We can automate the installation and updates of our VM by using user data within EC2

- Once we are at Step 3 of the above instance creation steps if we scroll down we can see advanced settings

<img width="959" alt="step3_config_inst_details" src="https://user-images.githubusercontent.com/110179866/185965249-72c1da1c-5d4e-495a-aaa6-24c8511d7faf.png">

- Once in advanced settings we can go to the user data text box and input a list of instructions utilising the following command `#!/bin/bash` to initialise the script

<img width="425" alt="binbash" src="https://user-images.githubusercontent.com/110179866/185965270-e932127a-063b-4d86-8050-bfa4fa2143b3.png">

- Then we continue on and select the other relevant settings and launch our instance, this may take longer than usual considering we are installing as we up the instance