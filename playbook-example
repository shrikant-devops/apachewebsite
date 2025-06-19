- hosts: all
  become: yes
  tasks:
    - name: update all the packages
      apt:
        name: "*"
        state: latest
    - name: Install apache httpd  (state=present is optional)
      ansible.builtin.apt:
        name: apache2
        state: present
    - name: Start service httpd, if not started
      ansible.builtin.service:
        name: apache2
        state: started
    - name: Install git
      ansible.builtin.apt:
        name: git
        state: present
    - name: Remove file (delete file)
      ansible.builtin.file:
         path: /var/www/html/
         state: absent
    - name: Git checkout
      ansible.builtin.git:
        repo: 'https://github.com/shrikant-devops/apachewebsite'
        dest: /var/www/html/

