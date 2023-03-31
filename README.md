# cloud1_42

## Automated Deployment on the Cloud

This project `cloud1` is an introduction to automated deployment on the cloud using the famous automation tool Ansible.

## Requirements

The subject states:

* Your site can restart automatically if the server is rebooted.
* In case of reboot all the data of the site are persisted (images, user accounts, articles, ...).
* It is possible to deploy your site on several servers in parallel.
* The script must be able to function in an automated way with for only assumption an ubuntu 20.04 LTS like OS of the target instance running an SSH daemon and
*ith Python installed.
* Your applications will run in separate containers that can communicate with each other (1 process = 1 container)
* Public access to your server must be limited and secure (for example, it is not possible to connect directly to your database from the internet).
* The services will be the different components of a WordPress to install by yourself. For example Phpmyadmin, MySQL, ...
* You must have a docker-compose.yml.
* You will need to ensure that your SQL database works with WordPress and PHP-MyAdmin.
* Your server should be able, when possible, to use TLS.
* You will need to make sure that, depending on the URL requested, your server redirects to the correct site.

## Repository Structure

```tree
.
├── ansible.cfg
├── group_vars
│   ├── all
│   │   ├── vars.yml
│   │   └── vault.yml
│   └── cloud1
│       └── vars.yml
├── inventory.yml
├── playbooks
│   └── init
│       └── cloud_1.yml
├── README.md
└── roles
    ├── docker
    │   └── tasks
    │       └── main.yml
    ├── hosts
    │   └── tasks
    │       └── main.yml
    ├── update
    │   └── tasks
    │       └── main.yml
    └── user
        └── tasks
            └── main.yml
```

- Groups under `group_vars/` either detail variables for a given target or all of them. The vault file will eventually hold all sensitive information and be encrypted with a secure password. This allows for specific variables to have specific values based on the target hosts or group of hosts.
- `inventory.yml` define the structure of groups and hosts in the project in relation to the structure of the `group_vars/` directory.
- `playbooks/init/`: each YAML file in this directory is mapped to a host or group and defines the order of execution of roles contained under `roles/`
- `roles/` a set of generic tasks to be executed on a given host based on a given playbook.
