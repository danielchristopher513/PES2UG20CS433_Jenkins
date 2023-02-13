pipeline {
    agent any
       stages {
         stage( 'Test') {
            steps {
              sh 'make -C main'
            }
         }
         stage( 'Deploy') {
          steps {
              sh 'mvn deploy'
              echo 'Deployment Successful '
          }
         }
       }
          post {
               failure {
                      echo 'Pipeline failed'
          }
         }
      }
