# DISASTER RECOVERY
![Blank diagram (6)](https://user-images.githubusercontent.com/110179866/186162202-7d931a49-215b-4141-b086-8e9060770bf0.jpeg)

### If any unexpected disasters occur we are prepared
#### For a production environment, it is important to take precautions so that you can recover if there’s an unexpected event. While Amazon RDS provides a highly available Multi-AZ configuration, it can’t protect from every possibility, such as a natural disaster, a malicious actor, or logical corruption of a database. To maintain business continuity, it is important to design and test a DR plan.


- Use multi AZ ie EU WEST 1a,b,c
- Use multi region, Ireland aswell as London
- If AWS goes down we use multi cloud deployment, AWS aswell as GCP/AZURE
- Hybrid cloud - localhost AND public cloud 


CRUD
create
read
update
delete

`$ aws s3 mb s3://eng122-pravin-bucket`

 `aws s3 cp test.txt s3://eng122-pravin-bucket`
