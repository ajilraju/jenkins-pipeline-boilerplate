pipeline {
    agent any
    triggers {
        cron('H * * * *')
    }
    stages {
        stage('Date') {
            steps {
                sh 'date'
            }
        }
    }
}
 