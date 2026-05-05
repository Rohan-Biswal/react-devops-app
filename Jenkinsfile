pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Pulls code from your GitHub repo
                git branch: 'main',
                    url: 'https://github.com/Rohan-Biswal/react-devops-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                // Builds the image and tags it as 'react-app'
                sh 'docker build -t react-app .'
            }
        }

        stage('Deploy') {
            steps {
                // Cleanup: Stops/removes existing container if it exists
                sh 'docker rm -f my-react-container || true'

                // Runs the new container
                sh 'docker run -d -p 80:80 --name my-react-container react-app'
            }
        }
    }
}