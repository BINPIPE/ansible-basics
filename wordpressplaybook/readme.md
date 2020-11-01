# Wordpress on Ubuntu 18.04 LAMP

This playbook will install a WordPress website on top of a LAMP environment (**L**inux, **A**pache, **M**ySQL and **P**HP) on an Ubuntu 18.04 machine. A virtualhost will be created with the options specified in the `vars/default.yml` variable file.

## Settings

- `php_modules`:  An array containing PHP extensions that should be installed to support your WordPress setup. You don't need to change this variable, but you might want to include new extensions to the list if your specific setup requires it.
- `mysql_root_password`: The desired password for the **root** MySQL account.
- `mysql_db`: The name of the MySQL database that should be created for WordPress.
- `mysql_user`: The name of the MySQL user that should be created for WordPress.
- `mysql_password`: The password for the new MySQL user.
- `http_host`: Your domain name.
- `http_conf`: The name of the configuration file that will be created within Apache.
- `http_port`: HTTP port for this virtual host, where `80` is the default. 

## Running this Playbook

Quickstart guide for those already familiar with Ansible:

### 1. Obtain the playbook
```shell
git clone https://github.com/do-community/ansible-playbooks.git
cd ansible-playbooks/wordpress-lamp_ubuntu1804
```

### 2. Customize Options

```shell
nano vars/default.yml
```

```yml
---
#System Settings
php_modules: [ 'php-curl', 'php-gd', 'php-mbstring', 'php-xml', 'php-xmlrpc', 'php-soap', 'php-intl', 'php-zip' ]

#MySQL Settings
mysql_root_password: "mysql_root_password"
mysql_db: "wordpress"
mysql_user: "sammy"
mysql_password: "password"

#HTTP Settings
http_host: "your_domain"
http_conf: "your_domain.conf"
http_port: "80"
```

### 3. Run the Playbook

```command
ansible-playbook -l [target] -i [inventory file] -u [remote user] playbook.yml
```
For running it on a localhost system use:

```command
ansible-playbook -l [target] -i [inventory file] playbook.yml --connection=local
```
which in this default state would look like this command:

```command
 ansible-playbook -i inventory playbook.yml --connection=local
```

