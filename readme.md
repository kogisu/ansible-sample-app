# Ansible Sample App

This is a simple Ansible playbook that creates a mongoDB, configures the DB, launches a httpd server in php on a remote server in a single command. This is based on a project made by kodekloud [learning app ecommerce](https://github.com/kodekloudhub/learning-app-ecommerce)

## Prerequisites

A machine (local or remote) as a controller node. The script can be installed and launch the application locally, or remotely on a separate machine (AWS, GCP, bare-metal)

## Launch Steps

1. Create an `inventory.txt` file with the hosts to install the services on.

```txt
server1 ansible_host=<server-ip> ansible_user=cloud_user ansible_ssh_pass=sample-pass
server2 ansible_host=<server-ip> ansible_user=cloud_user ansible_ssh_pass=sample-pass

[web]
server1
server2
```

2. Run ansible playbook

```sh
$ ansible-playbook ecommerce.yaml -i inventory.txt --extra-vars "ansible_sudo_pass=yourPassword"
```
