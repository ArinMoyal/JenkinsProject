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
               bash ${WORKSPACE}/C.c >> results
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
               bash ${WORKSPACE}/Python.py >> results
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
               ${WORKSPACE}/bash.sh >> results
           '''
      }
    }
     stage('Logging') {
       steps {
          echo 'Saving log file...'
          sh '''
              LOG_FILE="${HOME}/Projects/Jenkins/log"
              mkdir -p ${HOME}/Projects/Jenkins/
              if [ -f "${LOG_FILE}" ]; then
                echo "file ${LOG_FILE} exists"
              else
	              touch ${LOG_FILE}
              fi
	      date >> ${LOG_FILE}
	      echo "USER=$USER JOB_NAME=$JOB_NAME" >> ${LOG_FILE}
              echo "Build Number: $BUILD_NUMBER" >> ${LOG_FILE}
              cat "${WORKSPACE}/results" >> ${LOG_FILE}
	      echo "#############END OF LOG############" >> ${LOG_FILE}
            '''
      }
    }
  }
}
