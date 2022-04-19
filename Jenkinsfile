pipeline {
    agent any
    environment { 
        CC = 'gcc'
    }
    stages {
        stage('Checking compiler') {
            when {
                expression  { return CC == 'gcc' }
            }
            steps {
                sh 'printenv'
            }
        }
        stage('Build with branch') {
            when {
                branch pattern: "[cC]onditionals", comparator: "REGEXP"
            }
            steps {
                echo 'code is building'
            }
        }
        stage('All True') {
            when {
                allOf {
                    branch 'conditionals'
                    environment name: 'CC', value: 'gcc'
                }
            }
        }
    }
}