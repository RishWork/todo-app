pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
        stage('Code Quality Analysis') {
            steps {
                sh 'sonar-scanner'  // Assuming SonarQube is configured
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker-compose up -d'  // For Docker-based deployment
            }
        }
        stage('Release') {
            steps {
                sh 'aws deploy ...'  // Using AWS CodeDeploy
            }
        }
        stage('Monitoring and Alerting') {
            steps {
                sh 'datadog-agent start'  // Assuming Datadog is configured
            }
        }
    }
}
