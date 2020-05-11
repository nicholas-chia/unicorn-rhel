#Unicorn-RHEL demo instructions

With your Red Hat email address, join the Ansible Tower Demo Slack Team https://ansibletowerdemo.slack.com and go to #tower_notify channel to see notifications from your demo job runs.

1. Run Job Template __1 - Project Unicorn-RHEL - Launch AWS RHEL7 Instances needed for Unicorn__
   * Select __Username Inventory__ when prompted.
2. Run Job Template __2 - Project Unicorn-RHEL: Install Apps and Setup Web Servers__
   * Select __Username Inventory__ when prompted.
3. Run Job Template __3 - Project Unicorn-RHEL: Enable SSI on Apache__
   * Select __Username Inventory__ when prompted.
4. Go to __Inventory Tab__
   * Select __INVENTORIES / Username INVENTORY / AP-SOUTHEAST-1 / TAGS / TAG_ANSIBLE_GROUP / TAG_ANSIBLE_GROUP_LB__
   * Copy the __IP Address__ appearing on the right side (under HOSTS)
   * Paste the __IP Address__ on a new Browser window and __add :8888__ at the end
   * Click Enter to go __HAProxy load-balancer__ webpage at x.x.x.x:8888 
   * __Refresh Browser__ window to see Round-Robin load-balancing in effect (note the IP address changing)
5. Run Job Template __4 - Project Unicorn-RHEL: Performs a Rolling Update__
   * __Refresh Browser__ window to check progress of rolling update
6. Run Job Template __5 - Project Unicorn-RHEL: Delete all AWS RHEL Instances__

Using Angine Engine:

1. eval "$(ssh-agent -s)"
2. ssh-add ~/.ssh/ssh_key_pair.pem
3. ansible-playbook aws-launch.yml -e @extra_vars.yml -vvv
4. ansible-playbook -i aws_ec2.yml configure.yml -e @extra_vars.yml -vvv
5. ansible-playbook -i aws_ec2.yml deploy-app.yml -e @extra_vars.yml -vvv
6. ansible-playbook -i aws_ec2.yml enable-ssi.yml -e @extra_vars.yml -vvv
7. ansible-playbook -i aws_ec2.yml rolling-update.yml -e @extra_vars.yml -vvv
8. ansible-playbook -i aws_ec2.yml aws-delete-all.yml -e @extra_vars.yml -vvv

Sample extra-vars.yml
#aws
ec2_access_key: ChangeMe
ec2_secret_key: ChangeMe

#web servers instance count
ec2_instance_count: 2

#rh subscription manager
rhn_user: ChangeMe
rhn_pass: ChangeMe

#rh insights
display_name: ChangeMe

#web page
repository: ChangeMe>`
