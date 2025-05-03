pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/yourusername/my-node-app.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("my-node-app")
                }
            }
        }
        stage('Run Container') {
            steps {
                script {
                    dockerImage.run("-p 3000:3000")
                }
            }
        }
    }
}
