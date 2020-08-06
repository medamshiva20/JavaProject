---
- name: configure the CICD through Ansible playbook
  hosts: devserver
  tasks:
   - name: install the required softwares
     apt:
      name: "{{item.a}}"
      state: "{{item.b}}"
      update_cache: yes
     with_items:
      - {a: openjdk-8-jdk,b: present}
      - {a: maven,b: present}
      - {a: git,b: present}
   - name: Download the code from github
     git:
      repo: https://github.com/medamshiva20/JavaProject.git
      dest: /home/ubuntu/DevJob1/
   - name: Build the code
     shell: cd /home/ubuntu/DevJob1;mvn package
   - name: fetch artifact from the devserver
     fetch:
      src: /home/ubuntu/DevJob1/webapp/target/webapp.war
      dest: /tmp/
- name: Install the required softwares
  hosts: servers
  tasks:
   - name: Install the tomcat packages
     apt:
      name: "{{item.a}}"
      state: "{{item.b}}"
      update_cache: yes
     with_items:
      - {a: tomcat8,b: present}
      - {a: tomcat8-admin,b: present}
      - {a: openjdk-8-jdk,b: present}
      - {a: maven,b: present}
      - {a: git,b: present}
   - name: copy the users.xml file
     copy:
      src: /home/ubuntu/tomcat-users.xml
      dest: /etc/tomcat8/
- name: copy the articat to the qa server
  hosts: qaserver
  tasks:
   - name: copy the artifact
     copy:
      src: /tmp/172.31.50.185/home/ubuntu/DevJob1/webapp/target/webapp.war
      dest: /var/lib/tomcat8/webapps/qaenv1.war
   - name: Download the selenium program
     git:
      repo: https://github.com/medamshiva20/SeleniumTesting.git
      dest: /home/ubuntu/qa
   - name: Execute the selenium program
     shell: java -jar /home/ubuntu/qa/testing.jar
- name: copy the artifacts into prod server
  hosts: prodserver
  tasks:
   - name: copy the artifacts
     copy:
      src: /tmp/172.31.50.185/home/ubuntu/DevJob1/webapp/target/webapp.war
      dest: /var/lib/tomcat8/webapps/prodenv1.war
