pipeline {
  agent { node { label 'slave01' } }

   stages {
     stage ('C') {
       when {
         expression { ${LANGUAGE} == 'C'}
       }
       steps {
          echo "C selected"
          }
       }

     when {
         expression { ${LANGUAGE} == 'Python'}
       }
       steps {
          echo "Python selected"
          }
       }when {
         expression { ${LANGUAGE} == 'Bash'}
       }
       steps {
          echo "Bash selected"
          }
       }
   }
}
