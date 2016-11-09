#unicorn

1. Run 1 - Project Unicorn - Launch AWS Instances needed for Unicorn.
* Select <Username> Inventory when prompted.
2. Run 2 - Project Unicorn: Install Apps and Setup Web Servers
*Select <Username> Inventory when prompted.
3. Run 3 - Project Unicorn: Enable SSI on Apache
*Select <Username> Inventory when prompted.
4. Go to Inventory Tab
*Select INVENTORIES / <Username>INVENTORY / AP-SOUTHEAST-1 / TAGS / TAG_ANSIBLE_GROUP / TAG_ANSIBLE_GROUP_LB
*Copy the IP Address appearing on the left side
*Paste the IP Address on a new Browser window and add :8888 at the end
*Click Enter to go
*Refresh Browser window to see Round-Robin load-balancing in effect
5. Run 4 - Project Unicorn: Performs a Rolling Update
*Refresh Browser window to check progress of rolling update
6. Run 5 - Project Unicorn: Delete all AWS Instances
