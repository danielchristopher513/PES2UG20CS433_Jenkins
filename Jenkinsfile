pipeline {
    agent any
       stages {
           stage( 'Build') {
          steps {
              sh 'Build PES2UG20CS433-1'
              echo 'Build Successful '
          }
         }
           
           
         stage( 'Test') {
            steps {
              sh 'make -C main'
                echo 'Test Successful '
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
