pipeline {
    agent any
    environment {
        ENV_URL ="pipeline.google.com"
        SSHCRED =credentials('SSH_CRED') // env var 
    }

stages {
        stage('Stage One') {
            steps {
     
   sh '''
   echo demo
   env

'''
      echo "Name of the URL is ${ENV_URL}"
     
   
            }
        }
         stage('Stage two') {
            steps {
               echo "This is Stage two"
            }
        }
         stage('Stage three') {
            steps {
               echo "This is Stage three"
            }
        }
    }
}
