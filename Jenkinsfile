env.MYTOOL_VERSION = '1.33'
node {
    stage('Build') {
        echo "The number of stage is ${currentBuild.number} and status is ${currentBuild.currentResult} and branch is ${env.BRANCH_NAME}"
    }
    post {
        failure {
            script {
                echo "Pipeline Failed"
            }
        }
    }
}
