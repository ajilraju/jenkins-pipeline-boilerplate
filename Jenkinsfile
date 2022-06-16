pipeline {
    agent any
    stages {
        stage('Build 1') {
            steps {
                echo "Bulding project...."
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
