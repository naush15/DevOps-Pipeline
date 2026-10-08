pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building application...'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing application...'
            }
        }

        stage('Docker Build') {
            steps {
                bat 'docker build -t devops-pipeline .'
            }
        }

        stage('Deploy') {
            steps {
                bat 'docker run -d -p 8081:80 --name devops-container devops-pipeline'
            }
        }
    }
}