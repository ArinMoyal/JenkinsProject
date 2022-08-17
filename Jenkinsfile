pipeline {
  agent any
  stages {
    stage('Example Build') {
      steps {
        sh 'echo Hello World'
      }
    }
    stage('C script') {
      when {
        allOf {
          environment name: 'LANGUAGE', value: 'C'
          environment name: 'LANGUAGE', value: 'Any'
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
        allOf {
          environment name: 'LANGUAGE', value: 'Python'
          environment name: 'LANGUAGE', value: 'Any'
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
        allOf {
          environment name: 'LANGUAGE', value: 'Bash'
          environment name: 'LANGUAGE', value: 'Any'
      }
      steps {
        sh '''
               chmod 755 *.c
               bash ./bash.sh
           '''
      }
    }
  }
}
