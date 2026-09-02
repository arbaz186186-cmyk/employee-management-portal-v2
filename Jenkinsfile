pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t employee-portal:latest .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker stop employee-portal || true'
                sh 'docker rm employee-portal || true'
                sh 'docker run -d -p 80:80 --name employee-portal employee-portal:latest'
            }
        }
    }
}
