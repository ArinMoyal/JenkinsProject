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
        environment name: 'LANGUAGE', value: 'C'
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
        environment name: 'LANGUAGE', value: 'Python'
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
        environment name: 'LANGUAGE', value: 'Bash'
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
