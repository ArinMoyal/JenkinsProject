pipeline {
  agent { node { label 'slave01' } }

   stages {
     stage ('C') {
       steps {
         if ({$LANGUAGE} in ["C","all"]) {
          echo "C selected"
          }
       }
     }

     stage ('Python') {
       steps {
         if ({$LANGUAGE} in ["Python","all"]) {
          echo "Python selected"
          }
       }
     }     stage ('Bash') {
       steps {
         if ({$LANGUAGE} in ["Bash","all"]) {
          echo "Bash selected"
          }
       }
     }
   }
}
