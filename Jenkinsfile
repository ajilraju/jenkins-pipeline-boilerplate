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

// Example of PollSCM triggers

pipeline {

    agent any
    triggers { pollSCM('H * * * *')}
    stages {
        stage('Example of pollSCM') {
            steps {
                echo "Demo building"
            }
        }
    }
}
