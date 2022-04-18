pipeline {
    agent any
    stages {
        stage('Build 1') {
            echo "Bulding project...."
        }
        post {
            success {
                slackSend message: 'Build is successful on ${env.BRANCH_NAME} branch and build id #${env.BUILD_NUMBER}'
            }
        }
    }
}
