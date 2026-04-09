pipeline {
    agent any

    stages {

        stage('User Validation') {
            steps {
                script {
                    def user = currentBuild.rawBuild.getCause(hudson.model.Cause$UserIdCause)?.getUserId()

                    if (user != "devops1") {
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
