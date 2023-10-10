# ansible

-   ansible all --key-file ~/.ssh/ansible -i inventory -m ping
-   add ansible.cfg =>

*   Ping host: ansible all -m ping

*   View host lists: ansible all --list-host
*   ansible all -m gather_facts --limit ip

# Install apt module into sub server:

-   ansible all -m apt -a update_cache=true --become --ask-become-pass // 12345678
-   ansible all -m apt -a "name=vim-nox state=latest" --become --ask-become-pass
-   ansible all -m apt -a "upgrade=dist" --become --ask-become-pass
-   Install from yml: ansible-playbook --ask-become-pass install_apache.yml

# view ansible distribution:

-   ansible all -m gather_facts --limit <ip_server> | grep ansible_distribution

# ansible When condition:

-   When: ansible_distribution == "CentOS" and ansible_distribution_version == "8.2"

# add port

-   sudo firewall-cmd --add-port=80/tcp

# install package with improving

-   inventory: 18.183.117.198 apache_package=apache2 php_package=libapache2-mod-php
-   install_improving_apache.yml

# view tag

-   ansible-playbook --list-tag site.yml
-   Run with tag: ansible-playbook --tags centos --ask-become-pass site.yml
    --"centos, db"--

