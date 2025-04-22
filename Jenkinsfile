pipeline {
    agent any

    stages {
        stage('Clone repo') {
            steps {
                git 'https://your-repo-url.git'
            }
        }

        stage('Build Docker image') {
            steps {
                sh 'docker build -t churn-app .'
            }
        }

        stage('Run Docker container') {
            steps {
                sh 'docker-compose up -d'
            }
        }

        stage('Post-build') {
            steps {
                echo 'Deployment completed!'
            }
        }
    }
}
