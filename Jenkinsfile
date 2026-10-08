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
                sh 'docker build -t devops-pipeline .'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker rm -f devops-container || true'
                sh 'docker run -d -p 8081:80 --name devops-container devops-pipeline'
            }
        }
    }
}