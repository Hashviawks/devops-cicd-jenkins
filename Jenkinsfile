pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-app .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh '''
                docker stop my-app || true
                docker remove my-app || true
                docker run -d -p 5000:5000 --name my-app my-app
                '''
            }
        } 
    }
}