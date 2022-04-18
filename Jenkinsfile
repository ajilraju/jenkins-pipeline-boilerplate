pipeline {
    agent any
    options {
        timeout(time: 5, unit: 'SECONDS')
    }
    stages {
        stage('Example') {
            steps {
                sh 'sleep 10; true' // shell will timeout after the 5 elapsed.
            }
        }
    }
}