pipeline {
    agent any
    tools {
    maven 'M3'
  }
       stages {
          stage('Bui1d') {
                steps {
                   sh 'mvn clean install'
                   
                echo 'Build Stage Successful '
                }
          }
         stage( 'Test') {
            steps {
              sh 'mvn test'
                echo 'Test Stage successful'
                post {
                     always {
                     junit 'target/surefire-reports/* .xml '
                     }
                }
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
