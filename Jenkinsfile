pipeline {
    agent any

    stages {
        stage('Clone repo') {
            steps {
               git branch: 'main', url: 'https://github.com/DivyanshuKashyap15/Churn_model.git'
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
