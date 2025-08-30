pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                echo 'Building Docker Image...'
                sh """
                    docker build -t frontend:latest -f client/Dockerfile client/
                """
                sh """
                    docker build -t backend:latest -f server/Dockerfile server/
                """
            }
        }
        stage('Run Docker Image') {
            steps {
                echo 'Running Docker Image...'
                sh """
                    docker run --rm frontend:latest
                """
                sh """
                    docker run --rm backend:latest
                """
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                // Add your test steps here
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Add your deploy steps here
            }
        }
    }

    post {
        always {
            echo 'This will always run after the stages.'
        }
        success {
            echo 'This will run only if the pipeline succeeds.'
        }
        failure {
            echo 'This will run only if the pipeline fails.'
        }
    }
}