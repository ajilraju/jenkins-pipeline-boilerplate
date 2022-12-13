pipeline {
    agent any
    parameters {
        string(name: 'USER', defaultValue: 'ubuntu', description: 'Server connect username')
        string(name: 'SERVER_IP', description: 'Server ip address')
    }
    stages {
        stage('ssh examples') {
            environment {
                EC2_PUB_KEY = credentials('web-pub')
            }
            steps {
                sh '''
                    ssh -o 'StrictHostKeyChecking=no' -i $EC2_PUB_KEY $USER@$SERVER_IP command w
                '''
            }
        }
        stage('Creds Binding') {
            steps {
                withCredentials([sshUserPrivateKey(credentialsId: 'deploy-java-ssh-key', keyFileVariable: 'SSHPRIKEY', usernameVariable: 'SSHUSER')]) {
                    sh '''
                       ssh -o 'StrictHostKeyChecking=no' -i $SSHPRIKEY $SSHUSER@$SERVER_IP command w 
                    '''
                }
            }
        }
    }
}
