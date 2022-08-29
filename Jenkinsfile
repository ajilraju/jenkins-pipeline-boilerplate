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
    }
}