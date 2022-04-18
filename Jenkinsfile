pipeline {
    agent any
    parameters {
         choice(name: 'CHOICE', choices: ['No', 'Yes'], description: 'Pick something')
    }
    stages {
        stage('Test') {
            steps {
                echo "Testing the codes"
                sh 'if [ ${CHOICE} = Yes ]; then exit 1; fi'
            }
            post {
                failure {
                    echo "Job failed... Cleaning up"
                }
            }
        }
        stage('Build') {
            steps {
                echo "npm build"
            }
            post {
                always {
                    echo "I will always run"
                }
            }
        }
    }
}
