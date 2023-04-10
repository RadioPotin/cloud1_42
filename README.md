# Training Ansible

## Basic commands

Run the playbook, like this:

`ansible-playbook -i inventory.yaml playbook_role.yaml`

To delete everything, use this:

`ansible-playbook -i inventory.yaml playbook_clear.yaml`

To stop / start containers on a specific machine, use this:

`ansible-playbook -l cloud_1_host_1 playbook_start-containers.yaml`

## Dir overview

```
├── README.md
├── ansible.cfg
├── group_vars
│   └── virtualmachines.yaml
├── host_vars
│   ├── cloud_1_host_1.yaml
│   └── cloud_1_host_2.yaml
├── inventory
│   └── hosts.ini
├── inventory.yaml
├── playbook_clear.yaml
├── playbook_role.yaml
├── playbook_start-containers.yaml
├── playbook_stop-containers.yaml
└── roles
    └── docker-compose
        ├── files
        │   ├── hey.html
        │   ├── html/
        │   └── wordpressdb.sql
        ├── tasks
        │   └── main.yaml
        └── templates
            ├── default.conf.j2
            └── docker-compose.yaml
````

Helpful sources:
- [Ansible wordpress nginx playbook example](https://github.com/ansible/ansible-examples/tree/master/wordpress-nginx)
- [Xavki ansible tutorial](https://gitlab.com/xavki/devopsland/-/tree/master/ansible)

