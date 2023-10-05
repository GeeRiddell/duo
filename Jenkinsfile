pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh '''
                docker build -t seethatgee/duo-flask-jenkins:latest .
                '''
            }
        }
        stage('Push') {
            steps {
                sh '''
                docker push seethatgee/duo-flask-jenkins:latest 
                '''
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                kubectl rollout restart deployment flask-deployment
                '''

            }
        }
    }
}