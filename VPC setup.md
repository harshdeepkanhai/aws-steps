## AWS VPC Setup Steps
---------------
1. Go to AWS Console, search VPC and select it.
![image](https://user-images.githubusercontent.com/61924625/147456630-a426989f-ce4b-45b8-9193-afe36310572f.png)
2. Go to Left Pane, select "Your VPCs". Right Pane will show your VPCs and a button to "create VPC". Click on it
![image](https://user-images.githubusercontent.com/61924625/147456852-49c6e340-4e5b-493f-a4b0-923aa0d81d63.png)
![image](https://user-images.githubusercontent.com/61924625/147459245-1ba77bcd-e516-4b41-a49d-76552a885b4d.png)
3. Add Name Tag, IPv4 CIDR manual input and input 10.0.0.0/26 ( for 2^(32-26)=64IPs total), Let Tenancy be default.Click on "create VPC". Your VPC will be created.
![image](https://user-images.githubusercontent.com/61924625/147459558-359905c2-a9c4-40ef-aebf-6d4a3f9b262a.png)
![image](https://user-images.githubusercontent.com/61924625/147459581-c3cd8976-c9ca-4e47-9b29-2e04a8794410.png)
![image](https://user-images.githubusercontent.com/61924625/147459623-e17b231a-b2f3-4e6e-8a96-2f773b0cf94c.png)
![image](https://user-images.githubusercontent.com/61924625/147459660-0b9de8be-384e-4ead-976d-fae4cc411fab.png)

### Subnet Creation
--------------------
1. Go to Left Pane, Click on "Subnets". On the Right pane subnets will show. Click on "Create Subnet"
![image](https://user-images.githubusercontent.com/61924625/147461683-1d6aeee2-0225-4866-b8e6-4b90e0083905.png)
2. Select your VPC ID created in above VPC creation. In Subnet Settings. Select your subnet name, availability zone and CIDR (10.0.0.0/28 (16 IP Addresses)). Click on Add new subnet fill the above details and create 4 subnets(2 for public and 2 for private.)
![image](https://user-images.githubusercontent.com/61924625/147462216-9ee2786e-14f2-4925-a556-796b96b144b5.png)
![image](https://user-images.githubusercontent.com/61924625/147462249-ff7d15ee-2ed5-4ad3-bb21-dfe934268849.png)
![image](https://user-images.githubusercontent.com/61924625/147462275-373fb22a-ba2c-4d1f-9c55-4d3e5ebbbf68.png)
![image](https://user-images.githubusercontent.com/61924625/147462303-80d1bedd-39e2-4dda-a59d-68a78d1f0824.png)
![image](https://user-images.githubusercontent.com/61924625/147462331-3019bc8c-3db3-4c8f-9761-6ae279bcd2cb.png)

### Route Table Creation
-----------------------
1. Go to Left Pane, Click on Route Tables. On the Right pane all route tables wil show. Edit the name of route table associated with your VPC created in above steps and set it to public-rt.
![image](https://user-images.githubusercontent.com/61924625/147462637-1c2f30e8-8126-45f2-87ef-1004db87654c.png)
![image](https://user-images.githubusercontent.com/61924625/147462723-05c7ca75-bae6-4fd3-87a4-8c0382d224f4.png)
2. Click on "Create Route Table" and fill the name of the route table as private-rt and select the vpc created in above steps. Click on create route tables.
![image](https://user-images.githubusercontent.com/61924625/147462965-1337d1b6-c7bc-480d-b85c-713c59943b1f.png)
![image](https://user-images.githubusercontent.com/61924625/147462983-9c5a349f-2bd1-45a4-9f37-93b5827b02f8.png)
![image](https://user-images.githubusercontent.com/61924625/147462993-cf2aa357-16f0-49b8-84ca-6a2d47e1b55f.png)
3. Select Public-rt and click on actions and edit subnet associations
![image](https://user-images.githubusercontent.com/61924625/147463065-801e3098-e999-4691-aa1d-53f895a3f3ca.png)
4. Select the public-1 and public-2 subnets and click on save associations. Similarly do that for private-rt and private subnets.
![image](https://user-images.githubusercontent.com/61924625/147463341-d883f0f9-c79b-4f80-b40a-b0f74e5f92c7.png)
![image](https://user-images.githubusercontent.com/61924625/147463435-0bda239c-a88a-461d-88eb-289cfcbdc7fc.png)
5. Go to Left Pane, Click on Internet Gateway. On the Right pane all internet gateway will show.Click on Create Internet Gateways.
![image](https://user-images.githubusercontent.com/61924625/147463622-33921201-6e0c-4287-996b-eb09555aa45e.png)
6.Set the Name Tag and click on create Internet Gateway. Your internet gateway will be created.
![image](https://user-images.githubusercontent.com/61924625/147463767-410fbc94-d8bd-44c1-ad2f-92c337e7df11.png)
![image](https://user-images.githubusercontent.com/61924625/147463790-2fcde510-faf0-45bf-8eec-ba5b28fd5ef7.png)
7. Select your internet gateway, right click and select attach to VPC. Select your VPC created in above steps and click attach Internet Gateway.
![image](https://user-images.githubusercontent.com/61924625/147463853-ad8e03a5-6375-4c86-ba53-863e5d33bfaf.png)
![image](https://user-images.githubusercontent.com/61924625/147463935-d10c7164-d78f-434f-a414-105a73dd7071.png)
![image](https://user-images.githubusercontent.com/61924625/147463991-f659d77d-7030-4da2-88d7-d86dfd9bee8d.png)
8. Go to Route Tables. Select your public-rt and in the bottom pane select route tab and click on Edit routes
![image](https://user-images.githubusercontent.com/61924625/147464198-a754f5ef-de04-4ead-9904-d12035b568dc.png)
9. Add route 0.0.0.0/0 and Taget your created internet gateway. Click on save changes.
![image](https://user-images.githubusercontent.com/61924625/147464297-e2d93cbd-3568-48bf-b4ba-1d4e78d275e7.png)
10. Go to Left Pane, Click on NAT gateways. On the right pane it will show a list on NAT Gateways. Click on create NAT Gateways.
![image](https://user-images.githubusercontent.com/61924625/147464440-82420bd1-4103-4193-94d8-1bbdc4d2b30c.png)
11. Enter the NAT Gateway name and select a public subnet that you created and set the connectivity type to public. and click on allocate Elastic IPs and click on create NAT gateway
![image](https://user-images.githubusercontent.com/61924625/147464624-dfa3d428-6468-418d-9499-b34711691e80.png)
![image](https://user-images.githubusercontent.com/61924625/147464659-7ac22fa8-59d2-4a0f-9054-0c118173d56e.png)
![image](https://user-images.githubusercontent.com/61924625/147464746-ce6cdebb-3dc8-437e-a01a-20551af3f42a.png)
12. Go to Route Tables. Select your private-rt and in the bottom pane select route tab and click on Edit routes
![image](https://user-images.githubusercontent.com/61924625/147464849-c6a2d7df-769f-4015-8d4a-e41342394a13.png)
13. Add route 0.0.0.0/0 and Taget your created NAT gateway. Click on save changes.
![image](https://user-images.githubusercontent.com/61924625/147464922-d0125c26-c9d4-4cf7-8ea7-2475d480c6b6.png)
![image](https://user-images.githubusercontent.com/61924625/147464940-c958755d-d909-42fb-b394-3a3c3f5d435e.png)
14. Go to Subnets and select the public-1 subnet. Go to actions. Edit Subnet Settings. Select Enable auto-assign public IPv4 address and click on Save. Do it for public-2 subnet too.
![image](https://user-images.githubusercontent.com/61924625/147465162-7050e0b4-3766-429a-9d20-fe7b4e4f9e57.png)
![image](https://user-images.githubusercontent.com/61924625/147465305-f6d363f4-0472-4251-b6ea-e38adb7c5697.png)
![image](https://user-images.githubusercontent.com/61924625/147465330-d70f940a-5c90-4441-8b1e-ca4bac64583f.png)
![image](https://user-images.githubusercontent.com/61924625/147465354-3b6bf60f-8c9d-4d7f-b5cc-d3a6c311b570.png)

All steps done for network setup
👌





