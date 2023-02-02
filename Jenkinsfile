pipeline {
    agent any 
        stages {
            stage('Code') {
                steps {
                   git url:'https://github.com/CodeWithRushi/react_django_demo_app.git',branch:'main'
                }
                
            }
            stage('Build') {
                steps {
                    sh 'docker build . -t rushis750/django:latest'
                }
                
            }
            stage('push') {
                steps {
                    withCredentials([usernamePassword(credentialsId: 'DockerHub', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                    sh "docker login -u ${env.USERNAME} -p ${env.PASSWORD}"
                    sh "docker push rushis750/django:latest"
                    }
                }
            }
            stage('Test') {
                steps {
                    echo "Hello test"
                }
                
            }
            stage('Deploy') {
                steps {
                    sh "docker-compose down && docker-compose up -d"
                }
                
            }
        }
        
    
}
