pipeline {
    agent any
    
    stages {
        stage('Test Diff environment') {
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
                stage('Test QA') {
                    steps {
                        echo "Testing QA code"
                    }
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
 