pipeline {
    agent any
    environment { 
        CC = 'gcc'
    }
    stages {
        stage('Example') {
            environment { 
                AN_ACCESS_KEY = credentials('demo') 
            }
            steps {
                sh 'printenv'
                sh 'echo ${AN_ACCESS_KEY}'
            }
        }
    }
}