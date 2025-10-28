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
                bat 'docker tag registration:v1 akshara4/registration:v1'
                bat 'docker push akshara4/registration:v1'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f /Users/aksharagarlapad/Desktop/week-9-main/deployment.yaml'
                bat 'kubectl apply -f /Users/aksharagarlapad/Desktop/week-9-main2/service.yaml'
            }
        }
    }
}


