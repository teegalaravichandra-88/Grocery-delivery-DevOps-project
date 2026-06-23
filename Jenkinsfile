pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t grocery-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker stop grocery || true
                docker rm grocery || true
                docker run -d -p 5000:5000 --name grocery grocery-app
                '''
            }
        }
    }
}