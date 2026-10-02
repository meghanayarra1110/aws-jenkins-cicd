```groovy
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

        stage('Deploy') {
            steps {
                sh 'docker rm -f devops-cicd-app || true'
                sh 'docker run -d --name devops-cicd-app -p 80:80 devops-cicd-app'
            }
        }
    }

    post {
        success {
            echo 'CI/CD pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed!'
        }

        always {
            echo 'Pipeline execution finished.'
        }
    }
}
```
