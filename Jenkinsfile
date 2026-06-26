pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t babykart:v1 .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh '''
                docker rm -f babykart-container || true
                docker run -d --name babykart-container -p 8081:80 babykart:v1
                '''
            }
        }
    }
}
