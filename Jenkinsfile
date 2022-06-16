pipeline {
    agent any
    parameters {
        booleanParam(name: 'STATE', defaultValue: true, description: 'Choice Right or Wrong')
    }
    stages {
        stage('Build 1') {
            steps {
                script {
                    if (env.STATE) {
                        sh 'true'
                    } else  {
                        sh 'false'
                    }
                }
            }
            post {
                success {
                    slackSend color: "good", message: "The Build #${env.BUILD_NUMBER} is success: ${env.BUILD_URL}"
                }
                failure {
                    slackSend color: "danger", message: "The Build #${env.BUILD_NUMBER} is failed: ${env.BUILD_URL}"
                }
            }
        }
    }
}
