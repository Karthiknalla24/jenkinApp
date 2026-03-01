pipeline {
    agent any

    stages {

        stage('Build Maven') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t jenkinapp .'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker run -d -p 8000:8080 --name jenkinapp-container jenkinapp'
            }
        }
    }
}