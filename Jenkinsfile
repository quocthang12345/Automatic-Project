pipeline {
  agent any
  stages {
    stage('Build') {
      agent {
        dockerContainer {
          image 'node:16.13.1-alpine'
        }
      }
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
