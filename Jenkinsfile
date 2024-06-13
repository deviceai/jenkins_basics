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
               /* apt-get update */
                /* apk-get install -y lsb-release python3-pip */
                pip install -r requirements.txt --break-system-packages
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
