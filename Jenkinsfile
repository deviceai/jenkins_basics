pipeline {

    agent any

    triggers {
        pollSCM '*/5 * * * *'
    }

    stages {
        stage('build') {
            steps {
                echo 'Building..'
                sh 'python3 python_test.py'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}