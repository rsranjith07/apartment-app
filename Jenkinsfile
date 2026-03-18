pipeline {
    agent any

    environment {
        DOCKER_HUB = "ranjith5554"
    }

    stages {

        stage('Build') {
            steps {
                sh '''
                docker build -t $DOCKER_HUB/apartment-frontend:latest ./frontend
                docker build -t $DOCKER_HUB/apartment-backend:latest ./backend
                '''
            }
        }

        stage('Push') {
            steps {
                sh '''
                docker push $DOCKER_HUB/apartment-frontend:latest
                docker push $DOCKER_HUB/apartment-backend:latest
                '''
            }
        }

    }
}
