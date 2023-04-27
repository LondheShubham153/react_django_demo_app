# react_django_demo_app
A demo app for React and Django Deployment

docker-compose down
docker-compose up -d

Jenkins is built in Java,hence it is mandatory to hve java in your machine.
Jenkins is like a waiter/butler which waits for instructions.It is to automate tool to execute scripts.

Use use it daily as there are no changes in dockerfile or compose

A role of devops engineer is to build test deploy.
Bt How ?
-->With the help of CI/CD - Jenkins

//shell
echo "hello world"
docker-compose down
docker-compose up -d --no-deps --build web
//no-deps don't start any linked services and build again my application

----end of deliver---
---start of deploy---

//No need to click the build button you can automate the process by using webhook triggers.

process 

Jenkins configure 
webhook configure checkmark

//We will create a webhook url by using jenkins server ip 
$ http://3.89.143.234:8080/github-webhook/

restart the jenkins
When ever any thing is pushed pulled merged into github, github just triggered into webhook URL to send signal to jenkins.Webhook itself is a service runs in background. You have github integration pluggin installed hence jenkins will get to know and trigger the job again.

I docker killed my previous as it was in same port number.
