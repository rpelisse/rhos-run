ReadMe
====

To create instances on RHOS, deploy your clouds.yaml into the playbooks folder, and also a vm_settings.yaml file to provide default values for the VM configuration. Then run:

$ ansible-playbook -i inventory playbooks/playbook.yml

Here is an example of the inventory file:

[all]
my-instance-1 ansible_connection=local ansible_nodename=my_instance_name_1
my-instance-2 ansible_connection=local ansible_nodename=my_instance_name_2
...

Note that ansible_nodename must be provided, because gather_facts is set to false for effeciency purpose.

You can also delete the VM instead of creating them by changing the default value of 'state':

$ ansible-playbook -i inventory -e state=absent playbooks/playbook.yml
