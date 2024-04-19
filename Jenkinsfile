pipeline {

    agent any

    triggers {
        pollSCM '*/5 * * * *'
    }

    stages {
        stage('build') {
            steps {
                echo 'Building..'
                sh '''
                apk add --update python3
                cd myapp
                pip install -r requirements.txt
                '''  
            }
        }

        stage('Test') {
            steps {
                echo 'Testing..'
               /* sh 'python3 python_test.py' */
               sh '''
               cd myapp
               python3 hello.py --name=Alex
               '''
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}