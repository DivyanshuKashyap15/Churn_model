pipeline {
    agent any

    stages {
        stage('Clone repo') {
            steps {
               // git branch: 'main', url: 'https://github.com/DivyanshuKashyap15/Churn_model.git'
                git credentialsId: 'github-token', url: 'https://github.com/DivyanshuKashyap15/Churn_model.git'
            }
        }

        stage('Build Docker image') {
            steps {
                bat 'docker build -t churn-app .'
            }
        }

        stage('Run Docker container') {
            steps {
                bat 'docker-compose up -d'
            }
        }

        stage('Post-build') {
            steps {
                echo 'Deployment completed!'
            }
        }
    }
}
