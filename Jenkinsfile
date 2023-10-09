pipeline {
    agent {
      docker {
          image 'node:16.13.1-alpine'
          reuseNode true
      }
    }
    stages {

      stage('Build') {
          steps {
            bat "node --version"
            bat "ng --version"
            bat "ng build"
            archiveArtifacts artifacts: '**/dist/automatic/*.*', fingerprint: true
          }
      }
      stage('Test') {
          steps {
            bat "echo 'test'"
          }
      }
      stage('Deploy') {
          steps {
            bat "echo 'deploy'"
          }
      }
    }
}
