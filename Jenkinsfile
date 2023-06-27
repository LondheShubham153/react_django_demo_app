pipeline {
    agent { label "dev-agent" }
    stages{
        stage("Clone Code"){
            steps{
                git url: "https://github.com/farzshamim/react_django_demo_app.git", branch: "main"
            }
        }
        stage("Build and Test"){
            steps{
                sh "sudo docker build . -t react_django_demo_app"
            }
        }
        stage("Push to Docker Hub"){
            steps{
                withCredentials([usernamePassword(credentialsId:"dockerHub",passwordVariable:"dockerHubPass",usernameVariable:"dockerHubUser")]){
                sh "sudo docker tag react_django_demo_app ${env.dockerHubUser}/react_django_demo_app:latest"
                sh "sudo docker login -u ${env.dockerHubUser} -p ${env.dockerHubPass}"
                sh "sudo docker push ${env.dockerHubUser}/react_django_demo_app:latest"
                }
            }
        }
        stage("Deploy"){
            steps{
                sh "sudo docker-compose down && sudo docker-compose up -d"
            }
        }
    }
}
