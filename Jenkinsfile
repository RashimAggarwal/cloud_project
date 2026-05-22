pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git branch: 'main',
                url: 'https://github.com/RashimAggarwal/cloud_project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t 12308425/cloud_project .'
            }
        }

        stage('Push Docker Image') {
            steps {
                bat 'docker push 12308425/cloud_project'
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