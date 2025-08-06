pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/Akshith2623/jenkins-ci-cd-task.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("ci-cd-demo-app")
                }
            }
        }
        stage('Run Docker Container') {
            steps {
                script {
                    sh 'docker rm -f ci-cd-demo-app || true'
                    sh 'docker run -d --name ci-cd-demo-app -p 3000:3000 ci-cd-demo-app'
                }
            }
        }
    }
}
