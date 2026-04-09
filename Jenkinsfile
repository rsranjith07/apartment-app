pipeline {
    agent any

    stages {

        stage('User Validation') {
            steps {
                wrap([$class: 'BuildUser']) {
                    script {
                        echo "Triggered by: ${env.BUILD_USER_ID}"

                        if (env.BUILD_USER_ID?.toLowerCase() != "devops1") {
                         error "❌ Only DevOps can deploy"
                          }
                            
                        }
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
