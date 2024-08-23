pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Building"
            }
            post {
                success {
                    emailext body: 'Build was successful.',
                        subject: 'Build Status Email',
                        to: 'lguilding@deakin.edu.au'
                }
                failure {
                    emailext body: 'Build failed. Please check the logs for details.',
                        subject: 'Build Failure Notification',
                        to: 'lguilding@deakin.edu.au'
                }
            }
        }
        stage('Test') {
            steps {
                echo "Testing ..."
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying ..."
            }
        }
    }
}
