pipeline {
    agent any
    environment {
        ENV_URL ="pipeline.google.com"
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
