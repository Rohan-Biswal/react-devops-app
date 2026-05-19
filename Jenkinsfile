pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t react-app .'
            }
        }

        stage('Remove Old Container') {
            steps {
                sh 'docker rm -f my-react-container || true'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 80:80 --name my-react-container react-app'
            }
        }
    }
}