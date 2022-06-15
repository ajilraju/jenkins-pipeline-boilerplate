pipeline {
    agent any
    parameters {
        string(name: 'USER', description: 'Server connect username')
        string(name: 'SERVER_IP', description: 'Server ip address')
    }
    stages {
        stage('ssh examples') {
            environment {
                EC2_PUB_KEY = credentials('web-srv-pub')
            }
            steps {
                sh 'ssh -i $EC2_PUB_KEY $USER@$SERVER_IP'
            }
        }
    }
}