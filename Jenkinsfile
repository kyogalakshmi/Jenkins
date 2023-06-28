pipeline {
    agent any
    environment {
        ENV_URL ="pipeline.google.com"
        AN_ACCESS_KEY=credentials('SSH_CRED') // env var (AN_ACCESS_KEY) of jenkins
    }

stages {
        stage('Stage One') {
            steps {
   
   sh '''
   echo demo

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
