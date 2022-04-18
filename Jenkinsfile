pipeline {
    agent any
    stages {
        stage('Build 1') {
            steps {
                echo "Bulding project...."
            }
        }
        post {
            success {
                slackSend color: "good", message: 'Build is successful on ${env.BRANCH_NAME} branch and build id #${env.BUILD_NUMBER}'
            }
        }
    }
}
