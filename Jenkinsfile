pipeline {
    agent any
    parameters {
        booleanParam(name: 'STATE', defaultValue: true, description: 'Choice Right or Wrong')
    }
    stages {
        stage('Slack Notification') {
            steps {
                script {
                    if (env.STATE) {
                        sh 'exit 0'
                    } else  {
                        sh 'exit 1'
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
