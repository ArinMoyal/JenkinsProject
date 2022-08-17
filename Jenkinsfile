pipeline {
  agent any
  stages {
    stage('Initiation') {
      steps {
        sh 'printf "Initiating script.\n You chose ${LANGUAGE} programming language(s).\n Running ${LANGUAGE} script(s)."'
      }
    }
    stage('C script') {
      when {
        anyOf {
          environment name: 'LANGUAGE', value: 'C'
          environment name: 'LANGUAGE', value: 'All'
      }
      }
      steps {
        sh '''
               chmod 755 *.c
               bash ./C.c
           '''
      }
    }
    stage('Python script') {
      when {
        anyOf {
          environment name: 'LANGUAGE', value: 'Python'
          environment name: 'LANGUAGE', value: 'All'
      }
      }
      steps {
        sh '''
               chmod 755 *.py
               bash ./Python.py
           '''
      }
    }
    stage('Bash script') {
      when {
        anyOf {
          environment name: 'LANGUAGE', value: 'Bash'
          environment name: 'LANGUAGE', value: 'All'
      }
      }
      steps {
        sh '''
               chmod 755 *.sh
               ./bash.sh
           '''
      }
      }
 }
}
