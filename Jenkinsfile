pipeline {
  agent {
    docker {
      image 'node:16.13.1-alpine'
    }
  }
  environment {
    HOME="."
  }
  stages {
    stage('Build') {
      steps {
        // bat "node --version"
        // bat "ng --version"
        // bat "ng build"
        // archiveArtifacts artifacts: '**/dist/automatic/*.*', fingerprint: true

        script {
          /* the return value gets caught and saved into the variable MY_CONTAINER */
          MY_CONTAINER = bat(script: '@docker run -d -i node:16.13.1-alpine', returnStdout: true).trim()
          echo "mycontainer_id is ${MY_CONTAINER}"
          /* python --version gets executed inside the Container */
          bat "docker exec ${MY_CONTAINER} node --version "
          /* the Container gets removed */
          bat "docker rm -f ${MY_CONTAINER}"
        }
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
