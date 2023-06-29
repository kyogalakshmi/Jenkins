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
    //triggers { pollSCM('*/1 * * * *') }
stages {
stage('Parallel In Sequential') {
                    parallel {
                        stage('In Parallel 1') {
                            steps {
                                echo "In Parallel 1"
                            }
                        }
                        stage('In Parallel 2') {
                            steps {
                                echo "In Parallel 2"
                            }
                        }
                    
}
}
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
           
            //  input {
            //     message "Should we continue?"
            //     ok "Yes, we should."
            //     submitter "alice,bob"
            //     parameters {
            //         string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
            //     }
   
            // }
             steps {
               echo "This is Stage two"
                sh '''
              sleep 10
                '''
        }
            }
  
        
         stage('Stage three') {
            when {  anyOf {   //anyOf the condition met
                branch 'dev' 
                changeset "**/*.js" // when there is a change in .js file in dev env
            }
            }
            steps {
                sh '''
               echo "This is Stage three"
               echo -e "\\e[32m Hi \\e[0m" 
               
                '''
            }
        }
         stage('Stage four') {
        
            steps {
                sh '''
               echo "This is Stage four"
               echo -e "\\e[32m Hi \\e[0m" 
               

                '''
            }
        }
     
}
  post {
        always {  // always is a condition which will run always even it is passed / failed
            echo "I will always say Hello again!"
        clean ws //is used to clean the workspacr
        }
        aborted {
            echo "I will run again!"
        }
    }

}

