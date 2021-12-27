# EFS Setup
--------------
1. Go to AWS Console, search VPC and select it.
![image](https://user-images.githubusercontent.com/61924625/147456630-a426989f-ce4b-45b8-9193-afe36310572f.png)
2. Go to Left Pane, select "Security Groups". Right Pane will show your show security groups and a button to "create security group". Click on it
![image](https://user-images.githubusercontent.com/61924625/147466018-b9a65cba-becc-4b69-83cb-1d7aed4a2863.png)
3. Fill the basic details (Security Grouo Name, Description, select the VPC created in AWS VPC steps).
Add an inbound rule for NFS and select source default(we will change it later). Click on create security group.
![image](https://user-images.githubusercontent.com/61924625/147469800-aa53220f-87e8-42c3-aa94-9eeaf4ffc3d8.png)
![image](https://user-images.githubusercontent.com/61924625/147469869-fc588c89-fa17-490d-982d-f27f2ef53bb5.png)
4. Go to AWS Console, search EFS and select it.
![image](https://user-images.githubusercontent.com/61924625/147469904-2d7ed2f6-117a-4a05-b785-9349ed38e3fe.png)
![image](https://user-images.githubusercontent.com/61924625/147469932-4670b633-ac18-45ae-89b8-67231d615b01.png)
5. Click on create File System. and then customize
![image](https://user-images.githubusercontent.com/61924625/147470027-8b12f3a4-f800-42a2-a09c-7549cbec7a01.png)
6. Add name, single availability zone and the below shown options
![image](https://user-images.githubusercontent.com/61924625/147470176-59e35932-6a17-47a5-bd66-584922f373a7.png)
![image](https://user-images.githubusercontent.com/61924625/147470207-299dfdaa-539c-42a0-a181-f0ff8b48af05.png)
7. Click on Next
8. Select your VPC and mount targets. Add a private subnet and select security group as the created in above steps
![image](https://user-images.githubusercontent.com/61924625/147470398-dfd7be20-db99-4701-8eaa-e6f6dfec8806.png)
9. Click Next for Polict and Review and create click on create
![image](https://user-images.githubusercontent.com/61924625/147470484-588248b4-fd9c-46a8-8fc5-c887805ebfd7.png)

All steps done for EFS creation 👌


























