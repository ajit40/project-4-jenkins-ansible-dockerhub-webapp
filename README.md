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


exec commands
ansible-playbook /home/ansible/play.yml
