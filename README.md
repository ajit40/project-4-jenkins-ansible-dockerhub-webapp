# project-4-jenkins-ansible-dockerhub-webapp
project-4-git-jenkins-ansible-docker-dockerhub-webapp for students reference

jenkins : exec commands 

cd /home/ansible
docker build -t $JOB_NAME:v1.$BUILD_ID .
docker tag $JOB_NAME:v1.$BUILD_ID sakit333/$JOB_NAME:v1.$BUILD_ID
docker tag $JOB_NAME:v1.$BUILD_ID sakit333/$JOB_NAME:latest
docker push sakit333/$JOB_NAME:v1.$BUILD_ID
docker push sakit333/$JOB_NAME:latest
docker rmi $JOB_NAME:v1.$BUILD_ID sakit333/$JOB_NAME:v1.$BUILD_ID sakit333/$JOB_NAME:latest


exec commands : 

ansible-playbook /home/ansible/play.yml


---
- hosts: all
  become: true
  tasks:
    # - name: stop previous version docker
    #shell: docker stop qspider
    #- name: remove stopped container
    #shell: docker rm -f qspider
    #- name: remove docker images
    #shell: docker image rm -f sakit333/project-4
   - name: create docker image
     shell: docker run -it -d --name qspider -p 8090:8080 sakit333/project-4:latest

![image](https://github.com/sakit333/project-4-jenkins-ansible-dockerhub-webapp/assets/120071904/af72c49f-0f92-437d-b915-633eea3df244)

