# Ansible Basics |[![BINPIPE](https://img.shields.io/badge/YouTube-red.svg)](https://www.youtube.com/channel/UCPTgt4Wo0MAnuzNEEZlk90A)

Ansible is an IT automation tool that provides continuous deployment capabilities and zero downtime rolling updates. It’s simplicity, agentless features, and scalability is what makes it stand out. In this post, let’s discuss some common terms used in Ansible to get a better grasp of this tool.

## **Playbooks**

Developed in basic text language, Playbooks are human readable and form the basis of the configuration, deployment and orchestration language of Ansible. Some interesting functionalities of playbooks are:

-   Describe policies for remote systems.
-   Manage configurations and deployments of remote systems.
-   Zero downtime rolling updates.
-   Interact with monitoring servers and load balancers.

A playbook is a compilation of one or more plays. Each play in turn is responsible for mapping tasks to groups of hosts. Tasks are typically calls to Ansible modules.

```diff
+ Demo Playbook to Install Telnet on Ubuntu:
```
  <pre>
<a href="https://github.com/BINPIPE/ansible-basics/tree/main/testplaybook">https://github.com/BINPIPE/ansible-basics/tree/main/testplaybook</a>
</pre>

```diff
+ Demo Playbook to Install LAMP & Wordpress on Ubuntu:
```
<pre>
<a href="https://github.com/BINPIPE/ansible-basics/tree/main/wordpressplaybook">https://github.com/BINPIPE/ansible-basics/tree/main/wordpressplaybook</a>
</pre>


```diff
+ Playbook to Install Web based Mario Game on Ubuntu:
```
<pre>
<a href="https://github.com/BINPIPE/mariohtml5">https://github.com/BINPIPE/mariohtml5</a>
</pre>

```diff
+ Playbook to Install Netdata Monitoring Tool on Ubuntu with Ansible Galaxy Roles:
```
<pre>
<a href="https://github.com/BINPIPE/ansible-basics/tree/main/ansible-galaxy">https://github.com/BINPIPE/ansible-basics/tree/main/ansible-galaxy</a>
</pre>


## **Modules**

Ansible provides a module library or user-defined module that controls system resources. All modules support arguments, and most of them accept the key = value form. Data returned from modules are typically in the JSON format. Modules are idempotent, which means a change is made to the system only when the need arises.

A wide variety of modules are supported by the Ansible module library. A few of them include cloud, files, database, network, notification, packaging, system and web infrastructure modules.

## **Roles**

Roles help improve the organization of playbooks. These are nothing more than automation using the include directives. They are redistributable units which enables sharing of roles among playbooks.

## **Patterns**

Patterns control host management and help decide which hosts to communicate to and the configuration setup that needs to be applied to hosts. Patterns can be used in a variety of ways, including the targeting of all hosts, specific host, host by name, specific groups, and so on.

## **Facts**

Facts are automatically discovered information about remote nodes. This is achieved while running plays and executing the internal setup modules. Some example facts include: memory on all hosts, facts from Chef, and Puppet’s fact libraries (Ohai and Facter), etc.

## **Ansible Tower**

Ansible Tower is a web-based hub for all automation tasks. It provides the following functionalities:

-   Access Control
-   Secure sharing of SSH credentials
-   Graphical management of inventory
-   Inventory syncing with cloud sources
-   Logs of jobs
-   Autoscaling topologies support

## **Ansible Modes**

Ansible operates in various modes, including pull, push, check and diff modes. A brief description of these modes are:

-   Push mode: Ansible runs in this mode by default, providing fine-grained control over the systems it communicates with.
-   Pull mode: Pull mode is used when nodes are scheduled to be checked at an interval of N minutes.
-   Check mode: In this mode, Ansible runs with the — check option and indicates the changes that might occur with a command, if it’s run without using the check flag.
-   Diff mode: This mode helps identify the changes in the template files when overwritten.

## **Rolling Update**

The process of controlling N nodes to avoid failure due to simultaneous parallel updates is what is referred to as a rolling update. The number of nodes can be configured using the serial keyword in Ansible. The default value is the total number of nodes in the group under control.

## **Ansible Galaxy**

Ansible Galaxy refers to the free online community to download, view and rate Ansible roles.


___
:ledger: Maintainer: **[Prasanjit Singh](https://www.linkedin.com/in/prasanjit-singh)** | **www.binpipe.org**   [![BINPIPE](https://img.shields.io/badge/YouTube-red.svg)](https://www.youtube.com/channel/UCPTgt4Wo0MAnuzNEEZlk90A)
___ 
