pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f devops-app || true'
                sh 'docker run -d -p 5000:5000 --name devops-app devops-app'
            }
        }
    }
}