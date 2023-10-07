node {
  try {
    stage('Build') {
    echo "The number of stage is ${currentBuild.number} and branch is ${env.BUILD_NUMBER}"
  }
  } catch (e) {
    echo "Error Exception"
    throw e
  } finally {
    echo "status is ${currentBuild.currentResult}"
  }
}
