pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'sudo docker build -t grocery-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                sudo docker stop grocery || true
                sudo docker rm grocery || true
                sudo docker run -d -p 5000:5000 --name grocery grocery-app
                '''
            }
        }
    }
}