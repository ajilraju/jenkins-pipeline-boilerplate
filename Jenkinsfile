pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                sh 'sleep 3'
            }
        }
        stage('Build') {
            steps {
                sh 'sleep 3'
            }
        }
        stage('Deploy') {
            input {
                message "Approve the current deployment"
                ok "Approve"
                submitter "Admins"
            }
            steps {
                echo "Deployed."
            }
        }
        stage('Clean') {
            steps {
                echo 'cleaning workspace'
            }
        }
    }
}
