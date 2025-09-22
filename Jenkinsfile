pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t registration:v1 .'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                bat 'docker tag registration:v1 nagabhargavi71/registration:v1'
                bat 'docker push nagabhargavi71/registration:v1'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f D:/Devops/week12/deployment.yaml'
                bat 'kubectl apply -f D:/Devops/week12/service.yaml'
            }
        }
    }
}
