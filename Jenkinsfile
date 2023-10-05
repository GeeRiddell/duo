pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh '''
                docker build -t seethatgee/duo-jenkins:latest
                '''
            }
        }
        stage('Push') {
            steps {
                sh '''
                docker push seethatgee/duo-jenkins:latest
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