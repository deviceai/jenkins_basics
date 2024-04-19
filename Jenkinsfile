pipeline {

    /* agent any */
    agent { 
        node {
            label 'docker-agent-alpine'
            }
      }

    triggers {                       
        pollSCM '*/10 * * * *'        
    }                                

    stages {
        stage('build') {
            steps {
                echo 'Building..'
                sh '''
                cd myapp
                apk update
                apk add --update python3
                apk add --update py3-pip
                pip install package_name --break-system-packages
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