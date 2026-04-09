pipeline {
    agent any

    options {
        buildUserVars()
    }

    stages {

        stage('User Validation') {
            steps {
                script {
                    if (env.BUILD_USER_ID == null || env.BUILD_USER_ID != "devops1") {
                        error "❌ Only DevOps can deploy"
                    }
                }
            }
        }

        stage('Build') {
            steps {
                echo "🔧 Build started"
            }
        }

        stage('Deploy') {
            steps {
                echo "🚀 Deploy success"
            }
        }
    }
}
