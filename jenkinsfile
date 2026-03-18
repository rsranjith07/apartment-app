pipeline {
    agent any

    environment {
        DOCKER_HUB = "ranjith5554"
    }

    stages {

        stage('Clone') {
            steps {
                https://github.com/rsranjith07/apartment-app.git
            }
        }

        stage('Build Images') {
            steps {
                sh 'docker build -t $DOCKER_HUB/apartment-frontend:latest ./frontend'
                sh 'docker build -t $DOCKER_HUB/apartment-backend:latest ./backend'
            }
        }

        stage('Push Images') {
            steps {
                sh 'docker push $DOCKER_HUB/apartment-frontend:latest'
                sh 'docker push $DOCKER_HUB/apartment-backend:latest'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker-compose down || true'
                sh 'docker-compose up -d'
            }
        }
    }
}
