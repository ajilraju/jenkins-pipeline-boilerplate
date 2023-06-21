pipeline {
    agent any
    options {
        disableConcurrentBuilds()
        timestamps()
        retry(2)
    }
    stages {
        stage('sleep for 10s') {
            options {
                timeout(time: 5, unit: 'SECONDS')
            }
            steps {
                sh 'sleep 10; true' // shell will timeout after the 5 elapsed.
            }
        }
        stage('explicit errors') {
            steps {
                sh 'exit 1'
            }
        }
    }
}
