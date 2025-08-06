pipeline{
    agent any

    stages {
        stage('clone') {
            steps {
                git 'https://github.com/Akshith2623/jenkins-ci-cd-task.git'
            }
        }
    }

    stage('Build Docker Image'){
        steps {
            script {
                dockerImage = docker.Build("jenkins-ci-cd-app")
            }
        }
    }

    stage('Run Docker Container') {
        steps {
            script {
                dockerImage.run("-d -p 3000:3000")
            }
        }
    }
}