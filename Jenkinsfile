pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/meghanayarra1110/aws-jenkins-cicd.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-cicd-app .'
            }
        }

        stage('Test') {
            steps {
                sh 'docker image inspect devops-cicd-app'
            }
        }
    }
}
