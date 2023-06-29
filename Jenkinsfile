pipeline {
    agent any
    
    //  parameters {
    //     string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

    //     text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

    //     booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

    //     choice(name: 'ENV', choices: ['QA', 'DEV', 'CERT'], description: 'Enter a Env')

    //     password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    // }
    environment {
        ENV_URL ="pipeline.google.com"
        SSHCRED =credentials('SSH_CRED') // env var 
    }
     input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
triggers { pollSCM('*/1 * * * *') }
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
                sh '''
               echo "This is Stage three"
               echo -e "\\e[32m Hi \\e[0m" 

                '''
            }
        }
    }
}
