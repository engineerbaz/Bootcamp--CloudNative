

yum repolist


subscription-manager status
subscription-manager repos --list 

`subscription-manager repos --list | grep -i Ansible` for searching repo of Ansible , grep -i is ignore case 


`subscription-manager repos disable <repo name>` to disable repo 

/usr/bin/ansible anyone can execute


`ansible-doc` for Ansible Documentation
`ansible-doc -l` for list of  Ansible modules

`/etc/nsswitch.conf` for host entry

ansible init --disable > ansible.cfg 


ansible.cfg
--
[default]
inventory = ./inventory
ask_pass = true 
remote_user = root

---


`ansible -m ping server-a` to run simple ping as remote user 

**Create user and set password**
`ansible -m shell -a "useradd momo" server-b`
`ansible -m shell -a "echo password | passwd --stdin momo" server-b`


INI format (list style) for inventory file 

ansible ungrouped --list-host 









==-===----===

Ansible 
192.168.144.200

ansible --> ansible
root --> 12345


192.168.144.20

ansible --> ansible
root --> 12345



subscription-manager register --username "xxx@gmail.com" --password "ansdlna" --auto-attach
 
subscription-manager attach --pool=2c94c0f7843468e801845135aef04906


2c94b912843468890184515ed6f96411




## Ansible Modules 
- File Module 
  - copy
  - file
  - rsync
- Software package
  - yum
  - apt
  - pip
- System Module
  - firewalld
  - reboot
  - service
  - user
- Net Tool 
  - get_url
  - nmcli
  - uri = interect with web service 



ansible -m user -a 'name=newbie uid=4000 state=present



In **vi** you can set Tab Space to 2 by running `set ts=2` after pressing `:` in vi editor.


### Writing PlaybookR

var/lab3 
ansible.cfg
inventory 

  - name: "File for YAML"
    hosts: localhost
    remote_user: ansible
    tasks:
	# Creating the user 
      - name: Add the user 'Adam Listek' with a specific uid and a primary group of 'sudo'
        ansible.builtin.user:
        name: testpb
        comment: Test user from playbook
        uid: 1077
        group: testpb


=======


  - name: "Entry in resolve.conf"
    hosts: localhost
    remote_user: ansible
    tasks:
      - name: Writing data 
        ansible.builtin.lineinfile:
          line: "BAZ"
          dest: "/etc/resolve.conf"

  - name: "pring a msg"
    hosts: localhost
    tasks:
      - name: "print a msg using debug"
        debug:
          msg: "This is simple message"


ansible-doc -s yum shows docs in summarize 



**Array/list** 
It is in ordered form 
Like 
```yaml 
- name: testansible
  dest: "/tmp"
```
or  
`[name, dest]`


**dictionary**
It is in un-ordered form 

```yaml
name: tasks
action: new 
```
or 

`{happ: yes, class: 3}`

===

---
  - name: "Entry in resolve.conf"
    hosts: localhost
    remote_user: ansible
    tasks:
      - name: Writing data
        debug:
          msg: "Test msg"
      - name: create a user
        user:
          name: baz
          comment: Bashir
          uid: 8990
          shell: /bin/sh
          state: present
          groups: wheel
          append: yes
...


========

tasks:
 - name: latest version of httpd and firewalld installed
 yum:
 name:
 - httpd
 - firewalld
86 RH294-RHEL8.0-en-1-20200501
Chapter 3 | Implementing Playbooks
 state: latest
 - name: test html page is installed
 copy:
 content: "Welcome




 ===

 ### Variable



---
  - name: install 
    hosts: localhost
    vars:
      user: jane
      id: 387
    tasks:
      - name: print vars 
        debug:
          msg: "Pring Username {{user}} with ID {{id}}"
      - name: "Create user from Var {{user}}"
        user:
          name: "{{user}}"


...

---
  - name: install 
    hosts: server-a
    vars:
      user: jane
      id: 262879
      pwd: "shell@123"
    tasks:
      - name: print vars 
        debug:
          msg: "Pring Username {{user}} with ID {{id}}"
      - name: "Create user from Var {{user}}"
        user:
          name: "{{user}}"
          password: {{pwd}}
          home: "/var/tmp/{{user}}"
          uid: {{id}}
          shell: "/sbin/nologin"
          state: present


==

---
  - name: Deploy and start Apache HTTPD service
    hosts: webserver
    vars:
      web_pkg: httpd
      firewall_pkg: firewalld
      web_service: httpd
      firewall_service: firewalld
      python_pkg: python3-PyMySQL
      rule: http
   tasks:
     - name: Required packages are installed and up to date
 yum:
 name:
 - "{{ web_pkg }}"
 - "{{ firewall_pkg }}"
 - "{{ python_pkg }}"
 state: latest


 ==

---
- name: Deploy and start Apache HTTPD service
 hosts: webserver
 vars:
    web_pkg: httpd
    firewall_pkg: firewalld
    web_service: httpd
    firewall_service: firewalld
    python_pkg: python3-PyMySQL
    rule: http
 tasks:
 - name: Required packages are installed and up to date
 yum:
 name:
 - "{{ web_pkg }}"
 - "{{ firewall_pkg }}"
 - "{{ python_pkg }}"
 state: latest
 - name: The {{ firewall_service }} service is started and enabled
 service:
 name: "{{ firewall_service }}"
 enabled: true
 state: started
 - name: The {{ web_service }} service is started and enabled
 service:
 name: "{{ web_service }}"
 enabled: true
 state: started
 - name: Web content is in place
 copy:
 content: "Example web content"
 dest: /var/www/html/index.html
 - name: The firewall port for {{ rule }} is open
 firewalld:
------


ansible-vault create vars/myuser

ansible-vault edit vars/myuser
ansible-vault view vars/myuser

cat vars/mysuser


---
  - name: Create User
    hosts: devserver
    become: true
    remote_user: devops
    vars_files:
      - secret.yml
    tasks:
       - name: creating user from secret filename
         user:
            name: "{{ username }}"
            password: "{{pwhash}}"    


=====

ansible-playbook vars-dict.yaml --ask-pass 


ansible-vault create --vault-password-file=<filename> encryptedfile.yml

ansible-vault view --vault-password-file=<filename> encryptedfile



---====


---
  - name: Create User
    hosts: devserver
    tasks:
       - name: creating user from secret filename
         shell:
            cmd: echo "ki"
         register: result
       - name: print
         debug:
           var: result
        - name:
          debug:        
            msg: " {{result.stdout}} "

    

==


---
- name: Install remote facts
  hosts: webserver
  vars:
    remote_dir: /etc/ansible/facts.d
    facts_file: custom.fact
  tasks:
    - name: Create the remote directory
      file:
        state: directory
        recurse: yes
        path: "{{ remote_dir }}"
    - name: Install the new facts
      copy:
        src: "{{ facts_file }}"
        dest: "{{ remote_dir }}"


ansible servera.lab.example.com -m command -a 'systemctl status httpd'



---
- name: Install remote facts
  hosts: webserver
  tasks:
    - name: Install the required package
      yum:
        name: " {{ ansible_facts['ansible_local']['custom']['general']['package'] }}"
        state: latest
    - name: Start the Service
      service:
        name: " {{ ansible_facts['ansible_local']['custom']['general']['service'] }}"
        state: " {{ ansible['ansible_local']['custom']['general']['state'] }}"
        enabled: " {{ ansible['ansible_local']['custom']['general']['enabled'] }}"


====





firewall_pkg firewalld
firewall_svc firewalld
web_pkg httpd
web_svc httpd
ssl_pkg mod_ssl
httpdconf_src files/httpd.conf
httpdconf_dest /etc/httpd/conf/httpd.conf
htaccess_src files/.htaccess
secrets_dir /etc/httpd/secrets
secrets_src files/htpasswd
secrets_dest "{{ secrets_dir }}/htpasswd"
web_root /var/www/html

## Assignment

```yaml 

---
- name: Deploy and start Apache HTTPD service
  hosts: webserver
  vars:
    firewall_pkg: firewalld
    firewall_svc: firewalld  
    web_pkg: httpd
    web_svc: httpd
    ssl_pkg: mod_ssl
    httpdconf_src: files/httpd.conf
    httpdconf_dest: /etc/httpd/conf/httpd.conf
    htaccess_src: files/.htaccess
    secrets_dir: /etc/httpd/secrets
    secrets_src: files/htpasswd
    secrets_dest: "{{ secrets_dir }}/htpasswd"
    web_root: /var/www/html
  tasks:
    - name: Installing packages up todate
      yum:
        name: 
          - "{{web_pkg}}" 
          - "{{firewall_pkg}}" 
          - "{{ssl_pkg}}" 
        state: latest
    - name: Copy files 
      copy:
        src: "{{httpdconf_src}}"
        dest: "{{httpdconf_dest}}"
        owner: root
        group: root
        mode: '0644'
    - name: file 
      file:
        path: "{{secrets_dir}}"
        state: directory
        mode: '0500'
        owner: apache
        group: apache
        recurse: yes
    - name: Copy htpasswd 
      copy:
        src: "{{secrets_src}}"
        dest: "{{secrets_dest}}"
        owner: apache
        group: apache
        mode: '0400'
    - name: Copy .htaccess 6
      copy:
        src: "{{htaccess_src}}"
        dest: "{{ web_root }}/.htaccess"
        owner: apache
        group: apache
        mode: '0400'
    - name: Copy for index.html 7
      copy:
        content: "{{ ansible_facts.hostname }} {{ ansible_facts.default_ipv4.address }} has been customized by Ansible."
        dest: "{{ web_root }}/index.html"
    - name: The {{ firewall_service }} service is started and enabled
      service:
        name: "{{ firewall_svc }}"
        enabled: true
        state: started
    - name: The {{ web_service }} service is started and enabled
      service:
        name: "{{ web_svc }}"
        enabled: true
        state: started




```

### Assignment
==================

### Loop

---
- name: Loop 
  hosts: servera
  vars:
    mypackages:
      - httpd
      - python36
      - mariadb-server
      - vsftpd
    myservices:
      - httpd
      - mariadb
      - sshd
      - firewalld
  tasks:
    - name: "printing Variable Array"
      debug:
        var: mypackages
    - name: "Installing package"
      yum:
        name: "{{ mypackages }}"
        state: present        
    - name: "Start service "
      service:
        name: "{{ item }}"
        state: started
      loop: "{{ myservices }}"  

## Loop Item 

---
- name: Loop 
  hosts: servera
  tasks:
    - name: Create User 
      user:
        name: "{{ item.first_name }}"
        uid: "{{ item.uid }}"
        loop:
          - first_name : bilal
            user_id: 3234
          - first_name : anwer
            user_id: 6983
          


## Condition 

---
- name: Loop
  hosts: servera
  become: yes
  remote_user: root
  vars:
    os_name1: "Redhat is love"
    os_name2: "Debian is hard"
  tasks:
    - name: Print OS version
      debug:
        msg: "This is {{ ansible_facts.dns.nameservers }}"
      when: ansible_os_family == "RedHat"
    - name: Print OS version
      debug:
        msg: "The OS is {{ os_name2 }} "
      when: ansible_os_family == "Debian"

ansible_os_family


