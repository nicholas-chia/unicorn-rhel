#Unicorn-RHEL demo instructions

1. Run Job __1 - Project Unicorn-RHEL - Launch AWS RHEL7 Instances needed for Unicorn__
   * Select __Username Inventory__ when prompted.
2. Run Job __2 - Project Unicorn-RHEL: Install Apps and Setup Web Servers__
   * Select __Username Inventory__ when prompted.
3. Run Job __3 - Project Unicorn-RHEL: Enable SSI on Apache__
   * Select __Username Inventory__ when prompted.
4. Go to __Inventory Tab__
   * Select __INVENTORIES / Username INVENTORY / AP-SOUTHEAST-1 / TAGS / TAG_ANSIBLE_GROUP / TAG_ANSIBLE_GROUP_LB__
   * Copy the __IP Address__ appearing on the left side
   * Paste the __IP Address__ on a new Browser window and __add :8888__ at the end
   * Click Enter to go __HAProxy load-balancer__ webpage at x.x.x.x:8888 
   * __Refresh Browser__ window to see Round-Robin load-balancing in effect (note the IP address changing)
5. Run Job __4 - Project Unicorn-RHEL: Performs a Rolling Update__
   * __Refresh Browser__ window to check progress of rolling update
6. Run Job __5 - Project Unicorn-RHEL: Delete all AWS RHEL Instances__
