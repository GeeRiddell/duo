pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh '''
                docker build -t seethatgee/duo-nginx-jenkins:latest ./nginx
                '''
            }
        }
        stage('Push') {
            steps {
                sh '''
                docker push seethatgee/duo-flask-jenkins:latest .
                '''
            }
        }
        // stage('Deploy') {
        //     steps {
        //         sh '''
        //         kubectl apply -f .
        //         kubectl rollout restart deployment flask-deployment
        //         '''

        //     }
        // }
    }
}