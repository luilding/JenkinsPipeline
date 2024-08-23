stage('Test and Notify') {
    steps {
        echo 'Running integration tests'

    }
    post {
        always {
            emailext body: 'Test stage completed. Status: ${currentBuild.result}',
                     subject: 'Test Stage Notification',
                     to: 'lguilding@deakin.edu.au',
                     attachLog: true
        }
    }
}
