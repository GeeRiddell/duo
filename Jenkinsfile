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
        stage('Clean Up') { 
            steps {
                sh '''
                docker system prune -a --force
                '''
            }
        }        stage('Deploy') {
            steps {
                sh '''
                kubectl apply -f ./k8sdeploy
                kubectl rollout restart deployment flask-deployment
                '''

            }
        }
    }
}