pipeline {
    agent any
    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/sivaj07/my-website.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t mywebsite:latest .'
            }
        }
        stage('Deploy Container') {
            steps {
                sh 'docker rm -f mywebsite || true'
                sh 'docker run -d --name mywebsite -p 80:80 mywebsite:latest'
            }
        }
    }
}
