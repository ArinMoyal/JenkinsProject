pipeline {
  agent any
  stages {
    stage('Example Build') {
      steps {
        sh 'echo Hello World'
      }
    }
    stage('Example Deploy') {
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
  }
}
