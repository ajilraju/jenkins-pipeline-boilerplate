pipeline {
    agent any
    stages {
        stage('Build 1') {
            steps {
                echo "Bulding project...."
            }
            post {
                success {
                    slackSend color: "good", message: "Build is successful on ${BRANCH_NAME} branch and build id #${BUILD_NUMBER}"
                }
            }
        }
    }
}
