## Ansible Galaxy


**Ansible Roles**-

As you add more and more functionality and flexibility to your playbooks, they can become unwieldy and difficult to maintain. Roles allow you to break down a complex playbook into separate, smaller chunks that can be coordinated by a central entry point. 

**Ansible Galaxy**-

It is a repository of user contributed roles that you can add to playbooks to accomplish various tasks without having to write them yourself.
[https://galaxy.ansible.com](https://galaxy.ansible.com)


Now the below playbook containing just 6 lines of YAML can install `Apache Solr` by using ansible roles!

```code
---
- hosts: all
  roles:
    - geerlingguy.java
    - geerlingguy.tomcat6
    - geerlingguy.solr
  ```
  
  This is how we use roles:
  
  1. Download the roles from Ansible Galaxy with the command:
  
    ansible-galaxy install geerlingguy.java geerlingguy.tomcat6 geerlingguy.solr
  
  2. Execute the playbook with the command:
  
  `ansible-playbook -i inventory -l test solr.yml --connection=local`
  
  Essentially, the roles in Ansible Galaxy serve as building blocks that can be reused to make your installations faster, than having to write the entire playbooks in detail.
