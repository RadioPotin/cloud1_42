# Training Ansible

Run the playbook, like this:

ansible-playbook -i inventory.yaml playbook_role.yaml

To delete everything, use this:

ansible-playbook -i inventory.yaml playbook_clear.yaml

Helpful Sources:
[https://github.com/ansible/ansible-examples/tree/master/wordpress-nginx](ansible wordpress nginx playbook example)