pipeline {
    agent any
    triggers {
        cron('H * * * *')
    }
    stages {
        parallel {
            stage('Test Develop') {
                steps {
                    echo "Testing Develop code"
                }
            }
            stage('Test Prod') {
                steps {
                    echo "Testing Production code"
                }
            }
            stage('Test Prod') {
                steps {
                    echo "Testing Production code"
                }
            }
        }
        stage('Building') {
            steps {
                echo 'Building the source code'
            }
        }
    }
}
 