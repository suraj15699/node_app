pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/suraj15699/node_app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                   dockerImage = docker.build("my-python-app")
                }
            }
        }

        stage('Run Container') {
            steps {
                script {
                   dockerImage.run("-p 5000:5000")
                }
            }
        }
    }
}
