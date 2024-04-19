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
                cd myapp
                pip install -r requirements.txt
                '''
                
            }
        }

        stage('Test') {
            steps {
                echo 'Testing..'
               /* sh 'python3 python_test.py' */
               sh python3 hello.py --name=Alex
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}