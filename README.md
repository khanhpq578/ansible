# 1. Building an inventory

1. Create a file named inventory.ini in the ansible_quickstart directory that you created in the preceding step.

Add a new [myhosts] group to the inventory.ini file and specify the IP address or fully qualified domain name (FQDN) of each host system.

```bash
[myhosts]
192.0.2.50
192.0.2.51
192.0.2.52
```

2. Verify your inventory.

```bash
ansible-inventory -i inventory.ini --list
```

3. Ping the myhosts group in your inventory.

```bash
ansible myhosts -m ping -i inventory.ini
```

# 2. Creating a playbook

1. Create a file named playbook.yaml in your ansible_quickstart directory, that you created earlier, with the following content:

```bash
- name: My first play
  hosts: myhosts
  tasks:

  - name: Ping my hosts
    ansible.builtin.ping:

  - name: Print message
    ansible.builtin.debug:
    msg: Hello world
```

2. Run your playbook.

```bash
ansible-playbook -i inventory.ini playbook.yaml
```
