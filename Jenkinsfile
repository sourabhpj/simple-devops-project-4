pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                sh 'docker build -t sourabh .'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker stop sourabh || true'
                sh 'docker rm sourabh || true'
                sh 'docker run -d --name sourabh -p 80:80 sourabh'
            }
        }
    }
}