pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t registration:v1 .'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                sh 'docker tag registration:v1 akshara4/registration:v1'
                sh 'docker push akshara4/registration:v1'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f /Users/aksharagarlapad/Desktop/week-9-main/deployment.yaml'
                sh 'kubectl apply -f /Users/aksharagarlapad/Desktop/week-9-main2/service.yaml'
            }
        }
    }
}



