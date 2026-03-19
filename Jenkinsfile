pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t ranjith5554/apartment-frontend:latest ./frontend'
                sh 'docker build -t ranjith5554/apartment-backend:latest ./backend'
            }
        }

        stage('Push') {
            steps {
                sh 'docker push ranjith5554/apartment-frontend:latest'
                sh 'docker push ranjith5554/apartment-backend:latest'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                docker-compose down
                docker-compose pull
                docker-compose up -d
                '''
            }
        }
    }
}
