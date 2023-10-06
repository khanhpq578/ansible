# ansible

-   ansible all --key-file ~/.ssh/ansible -i inventory -m ping
-   add ansible.cfg =>

*   Ping host: ansible all -m ping

*   View host lists: ansible all --list-host
*   ansible all -m gather_facts --limit ip
*   Install apt module into sub server: ansible all -m apt -a update_cache=true --become --ask-become-pass // 12345678
    ansible all -m apt -a "name=vim-nox state=latest" --become --ask-become-pass
    ansible all -m apt -a "upgrade=dist" --become --ask-become-pass
