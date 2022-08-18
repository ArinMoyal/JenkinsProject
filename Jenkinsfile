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
     stage('Logging') {
       steps {
          echo 'Saving log file...'
          sh '''
              report_file="${HOME}/Projects/Jenkins/log"
              mkdir -p ${HOME}/Projects/Jenkins/
              if [ -f "${report_file}" ]; then
                echo "file ${report_file} exists"
              else
	              touch ${report_file}
              fi
	      date >> ${report_file}
	      echo "USER=$USER JOB_NAME=$JOB_NAME" >> ${report_file}
              echo "Build Number: $BUILD_NUMBER" >> ${report_file}
              cat "${WORKSPACE}/scripts/results" >> ${report_file}
	      echo "#############END OF LOG############" >> ${report_file}
            '''
      }
    }
  }
}
