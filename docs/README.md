1. Install Ansible.
   pip install ansible

---

# Building an inventory

1. Create a file named inventory.ini in the ansible_quickstart directory that you created in the preceding step.

2. Add a new [myhosts] group to the inventory.ini file and specify the IP address or fully qualified domain name (FQDN) of each host system.
   [myhosts]
   192.0.2.50
   192.0.2.51
   192.0.2.52

3. Verify your inventory.
   ansible-inventory -i inventory.ini --list 4. Ping the myhosts group in your inventory.
   ansible myhosts -m ping -i inventory.ini

---

ssh-copy-id -i /Users/lisod/projects/libs/ansible/ssh/ansible.pub -f -o "IdentityFile ~/.ssh/" ubuntu@

helm install --namespace gitlab-runner --create-namespace --set runnerRegistrationToken=cXA1yZzo4Qfk-yaTRQWb gitlab-runner gitlab/gitlab-runner --version v0.63.0 --values values.yaml
