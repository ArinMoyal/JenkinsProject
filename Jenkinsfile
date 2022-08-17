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
        branch 'main'
        environment name: 'LANGUAGE', value: 'C'
      }
      steps {
        sh 'echo Deploying'
      }
    }
  }
}
