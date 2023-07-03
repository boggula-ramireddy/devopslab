sudo apt-get update
       sudo apt-get install docker.io -y
       sudousermod -aG docker $USER &&newgrp docker
       curl -LO http://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
       sudo install minikube-linux-amd64 /usr/local/bin/minikube
       sudo snap install kubectl --classic
       minikube start --driver=docker
       minikube status
       kubectl get pods
       kubectl get svc
      kubectl create deployment hello-node --image=k8s.gcr.io/echoserver:1.4
       kubectl expose deployment hello-node --type=NodePort --port=8080
       kubectl get svc
		NAME         TYPE        CLUSTER-IP     EXTERNAL-IP   PORT(S)          AGE
		hello-node   NodePort    10.108.92.61   <none>        8080:30025/TCP   3m36s
		kubernetes   ClusterIP   10.96.0.1      <none>        443/TCP          9m49s
	 minikube ip
	 curl 192.168.49.2:30025 
	 minikube service hello-node



  6.curl -fsSL https://get.docker.com -o install-docker.sh
      sh install-docker.sh
      docker --version
      sudo su -
      docker pull tomee
      docker image ls
      docker pull maven
      docker pull jenkins/jenkins
      docker image ls
      docker container ls
      docker run --name  myjenkins  -p 7070:8080    -d   jenkins/jenkins
      docker container ls
      docker run --name mydb -d -e MYSQL_ROOT_PASSWORD=ajay007 mysql:5
      docker container ls
      docker   exec   -it  mydb bash
      sudo curl -L "http://github.com/docker/compose/releases/download/1.24.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
      sudo chmod +x /usr/local/bin/docker-compose
      docker-compose --version
      docker pull httpd
      vim docker-compose.yml	
	---
version: '3'

services:
 mydb:
  image: mysql:5
  environment:
   MYSQL_ROOT_PASSWORD: ajay007

 apache:
  image: httpd
  ports:
   - 6060:8080
  links:
   - mydb:mysql


 php:
  image: php
  links:
   - mydb:mysql
   - apache:tomcat
...
      docker-compose up -d
      docker container ls
      docker ps -a


     
