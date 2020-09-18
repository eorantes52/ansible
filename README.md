# Ansible
Ansible is a universal language, unraveling the mystery of how work gets done. Turn tough tasks into repeatable playbooks. Roll out enterprise-wide protocols with the push of a button. Ref: https://www.ansible.com/

In this repo we'll find playbooks to automate, orchestrate and mantain AWS resources like RDS, Route53 and EC2


## Usage
To execute any of the plabooks you have to send the variables that playbook needs as a parameter, as shown below:

```
ansible-playbook --extra-vars="target=localhost src=${SRC} dest=${DEST}" playbook.yml
```

Or you can create a vars.yml file:
-

```
Key1: "value1"
Key2: "value2"
Key3: "value3"
Key4: "value4"
```
And then add the vars.uml file into the playbok:
 
 ```
 - name: Deploy win
  hosts: "{{ target }}"
  vars_files:
    - vars.yml
  tasks:
 ```