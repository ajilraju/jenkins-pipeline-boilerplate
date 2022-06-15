pipeline {
    agent any
    // pipeline scope env
    environment { 
        CC = 'gcc'
    }

    stages {
        stage('Listing env') {
            steps {
                sh 'printenv'
            }
        }
        stage('Using env vars') {
            steps {
                //groovy string
                echo "Current Build Number #${env.BUILD_NUMBER}"
                //shell script strings
                sh 'echo "Current Build Number# $BUILD_NUMBER"'
            }
        }
        stage('Stage level env') {
            environment {
                USER_NAME = 'Tom'
            }
            steps {
                echo "The user ${env.USER_NAME} is a DevOps Engineer"
                script {
                    env.USER_GRT = 'Hello!!!'
                }
                echo "${env.USER_GRT} ${env.USER_NAME}"
            }
        }
        stage('WithEnv scope') {
            steps {
                withEnv(["NAME=Thomas", "POS=DevOps"]) {
                    echo "${env.NAME} is a ${env.POS}"
                }
            }
        }
        stage('Shell return') {
            environment {
                NO_OF_USERS = sh(script: 'cat /etc/passwd | wc -l', returnStdout: true).trim()
            }
            steps {
                echo "No of users in the system is ${env.NO_OF_USERS}"
            }
        }
    }
}