pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/RashimAggarwal/cloud_project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t 12308425/cloud_project .'
            }
        }

        stage('Push Docker Image') {
            steps {
                sh 'docker push 12308425/cloud_project'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }
    }
}