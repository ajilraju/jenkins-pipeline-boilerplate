pipeline {
    agent any
    stages {
        stage('declarative') {
            steps {
                echo 'Hello World'
            }
        }
        stage('scripted') {
            steps {
                echo 'Hello World'

                script {
                    def browsers = ['chrome', 'firefox', 'edge', 'safari']
                    if (browsers.size() > 1) {
                        for (int i = 0; i < browsers.size(); ++i) {
                            echo "Testing the ${browsers[i]} browser"
                        }
                    }
                }
            }
        }
        stage('Odd or Even') {
            steps {
                script {
                    if (currentBuild.number % 2 == 0) {
                        echo "It's an Even number build"
                    } else {
                        echo "It's an Odd number build"
                    }
                }
            }
        }
    }
}