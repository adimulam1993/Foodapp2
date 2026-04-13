pipeline {
    agent any

    environment {
        KUBECONFIG = 'C:\\Users\\Koniki Harika\\.kube\\config'
    }

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/adimulam1993/FoodApp.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t foodapp .'
            }
        }

        stage('Test Kubernetes Connection') {
            steps {
                bat 'kubectl get nodes'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f deployment.yaml'
                bat 'kubectl apply -f service.yaml'
            }
        }
    }
}
