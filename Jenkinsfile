pipeline {
  agent { node { label 'slave01' } }

   stages {
      stage('Clone Sources') {
        steps {
          checkout scm
        } 
      }
      stage('Execute C exe file') {
         steps {
            echo 'Compilation process..'
            sh '''
            '''
            sh '''
                echo "Running bin file"
                
            '''
         }
      }
      stage('Execute python script') {
         steps {
            echo 'Execute python script'
            echo 'imagine this actually did something'
            
         }
      }
      stage('Execute bash script') {
         steps {
            echo 'bash script..'
         }
      }
      
   }
}
