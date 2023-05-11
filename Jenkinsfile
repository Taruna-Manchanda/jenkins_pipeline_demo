pipeline {
      agent any
      stages {
          stages('One') {
              steps {
                  echo 'hi , stage 1'
              }
          }
          stages('Two') {
              steps {
                  input('hi , do you wantt to proceed')
  
              }
          }
  
          stages('Three') {
              parallel {
                  stage('unit test') {
                      steps {
                          echo 'running unit test'
  
                      }
                  }
                  stage('integration test') {
                      agent {
                          docker {
                          reuseNode false ( reusenode by default false not use global agent sepeficed at root evel which is any
                                  image 'ubuntu'
                              }
                      }
                      steps {
                          echo 'running integration test'
  
                      }
                  }
              }
          }
