pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/yourusername/hello-world-app.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("hello-world-app:latest")
                }
            }
        }
        stage('Run Docker Container') {
            steps {
                script {
                    docker.image("hello-world-app:latest").run("-p 3000:3000")
                }
            }
        }
    }
    post {
        success {
            echo 'Application deployed successfully!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
