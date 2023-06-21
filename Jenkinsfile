pipeline {
    agent any
    parameters {
        string(name: 'USER', defaultValue: 'ubuntu', description: 'Username for server connection')
        string(name: 'SERVER_IP', description: 'IP address of the server')

    }
    stages {
        stage('ssh examples') {
            environment {
                EC2_PUB_KEY = credentials('<creds id>')
            }
            steps {
                sh '''
                    ssh -o 'StrictHostKeyChecking=no' -i ${EC2_PUB_KEY} ${USER}@${SERVER_IP} command hostname; whoami
                '''
            }
        }
        stage('Creds Binding') {
            steps {
                withCredentials([sshUserPrivateKey(credentialsId: 'deploy-java-ssh-key', keyFileVariable: 'SSHPRIKEY', usernameVariable: 'SSHUSER')]) {
                    sh '''
                       ssh -o 'StrictHostKeyChecking=no' -i ${SSHPRIKEY} ${SSHUSER}@${SERVER_IP} command hostname; whoami
                    '''
                }
            }
        }
    }
}
