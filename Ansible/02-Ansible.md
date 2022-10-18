# Ansible



ansible demo -a "ls"
ansible demo -b -m yum -a "pkg=httpd state=present"


`ansible demo[0] -b -m yum -a "pkg=httpd state=present"` for installation 
`ansible demo[0] -b -m service -a "name=httpd state=started"` for starting services #Module service 

`'ansible demo0] -b -m user -a “name=testansible group=testansible password=ansible"`
for adding user

ansible demo[0] -m group -a “name=testansible state=present”

## Playbook 
Combination of tasks in a singe file using YAML


```yaml 
- name: Update web servers
  hosts: webservers
  remote_user: root

  tasks:
  - name: Ensure apache is at the latest version
    ansible.builtin.yum:
      name: httpd
      state: latest
  - name: Write the apache config file
    ansible.builtin.template:
      src: /srv/httpd.j2
      dest: /etc/httpd.conf

```

ansible-playbook main.yml -u ansible --become


---




```yaml
---
- name: Ansible Create user functionlity module demo
  hosts: 192.168.144.201
  remote_user: ansible
  tasks:
	# Creating the user 
    - name: Add the user 'Adam Listek' with a specific uid and a primary group of 'sudo'
      ansible.builtin.user:
        name: testpb
        comment: Test user from playbook
        uid: 1077
        group: testpb
        createhome: yes        # Defaults to yes
        home: /home/testpb   # Defaults to /home/<username>




```
### Sample 

```yaml
- hosts: all
  tasks:
  - name: Creating an empty file
    file:
      path: "/your path"
      state: touch
```

```yaml 
- hosts: all    # List of hosts 
  user: ansible
  connection: ssh
  become: yes
  gather_facts: yes 
```

## Install and Start Sercice
```yaml 
- hosts: 192.168.144.201
  user: ansible
  connection: ssh
  become: yes
  gather_facts: yes
  tasks:
    - name: install httpd
      action: yum name=httpd state=installed
    - name: start httpd
      action: service name=httpd state=started

```

```yaml
- hosts: 192.168.144.201
  user: ansible
  connection: ssh
  become: yes
  gather_facts: yes
  tasks:
#    - name: install httpd
#      action: yum name=httpd state=installed
    - name: stop httpd
      action: service name=httpd state=stopped
```


#### Variable


```yaml
---
- hosts: 192.168.144.201
  vars:
    - username: ansible
    - home: /home/ansible   
  tasks:
    - name: print variables
      debug:
        msg: "Username: {{ username }}, Home dir: {{ home }}"

```


## Variables

```yaml
- hosts: 192.168.144.201
  user: ansible
  connection: ssh
  become: yes
  gather_facts: yes
  vars:
    pak: httpd
  tasks:
    - name: install httpd
      action: yum name='{{pak}}' state=installed
```


- hosts: 192.168.144.201
  user: ansible
  connection: ssh
  become: yes
  gather_facts: yes
  vars:
    pak: httpd
  tasks:
    - name: install httpd
      action: yum name='{{pak}}' state=installed
  handlers:
    - name: restart httpd
      service:
        name: service name
        state: restarted

---

- hosts: 192.168.144.201
  user: ansible
  connection: ssh
  become: yes
  gather_facts: yes
  vars:
    pak: httpd
  tasks:
    - name: install httpd
      action: yum name='{{pak}}' state=installed
  handlers:
    - name: Start httpd
      service:
        name: service name
        state: started



```yaml
- hosts: 192.168.144.201
  user: ansible
  connection: ssh
  become: yes
  gather_facts: yes
  tasks:
    - name: install httpd
      action: yum name=httpd state=installed
      notify:
        - start httpd
  handlers:
    - name: start httpd
      service:
        name: httpd
        state: started
 
```

`ansible-playbook handle3.yaml --check` for checking 



`ansible-vault create testencyrpt.yaml` for making encrypted file

` ansible-playbook --ask-vault-pass encrypt.yaml` for running encrypted files 


---
```yaml
- name: Loop Register Test
  gather_facts: no
  hosts: 192.168.144.201
  tasks:
    - name: Looping Echo Task
      shell: "echo This is my item: {{ item }}" loop:
        - one
        - two
      register: echo_results
    - name: Show echo_results variable
      debug:
        msg: "STDOUT from previous task: {{ item.stdout }}" loop: "{{echo_results['results'] }}"
```

```yaml


- name: Demonstrate the "in" keyword 
  hosts: all
  gather_facts: yes 
  vars:
    supported_distros:
      - RedHat
      - Fedora 
  tasks:
    - name: Install httpd using yum, where supported yum:
        name: http 
        state: present
      when: ansible_distribution in supported_distros
```










==========




================================
---
- name: Ansible Create user functionlity module demo
  hosts: web # Defining the remote server inventory host group
	# Defining the remote server where the ansible create user module 
  # will manage the objects
  remote_user: ubuntu # Using Remote user as ubuntu
  tasks:

	# name - Defines the username that is present or to create
	# groups - Adds users in secondary groups or use groups
	# state: present - Creates a user or works with a user
	# state: absent - Deletes a user
	# shell - Specifies shell-type a user can work on
	# home - Sets a user’s home directory
	# createhome: yes - Create a home directory for a user 
	# createhome: no - Do not create a home directory for a user

	# Creating the user Adam Listek 
    - name: Add the user 'Adam Listek' with a specific uid and a primary group of 'sudo'
      ansible.builtin.user:
        name: adamlis
        comment: AdamListek
        uid: 1077
        group: sudo
        createhome: yes        # Defaults to yes
        home: /home/adamlis    # Defaults to /home/<username>

	# Adding the user qa_editor in the editor group 
    - name: Add group "editor" to remote node
      group:
        name: qa_editor
        gid: 2212
        state: present

	# Adding the user Rochela in the qa_editor group and bash shell
    - name: Add the user 'Rochella' with a bash shell, appending the group 'editor' to the user's groups
      ansible.builtin.user:
        name: rochella
        shell: /bin/bash
        groups: qa_editor
        append: yes

# Removing the user shanky from the system 
    - name: Remove the user 'Shanky' if present in the linux system
      ansible.builtin.user:
        name: shanky3
        state: absent
        remove: yes

-----

