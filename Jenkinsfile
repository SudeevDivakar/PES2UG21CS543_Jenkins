pipeline {
    agent any
    stages {
          stage('Clone repository') {
              steps {
                  checkout([$class: 'GitSCM',
                  branches: [[name: '*/main']],
                  userRemoteConfigs: [[url: 'https://github.com/SudeevDivakar/PES2UG21CS543_Jenkins.git']]])
              }
          }
          stage('Build') {
              steps {
                  build 'PES2UG21CS543-1'
                  sh 'gcc main.cpp -o output'
              }
          }
          stage('Test') {
              steps {
                  sh './output'
              }
          }
          stage('Deploy') {
              steps {
                  echo 'deploy'
              }
          }
    }
    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
            
