pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Building"
            }
            post {
                success {
                    emailext (
                        to: "lguilding@deakin.edu.au",
                        subject: "Build Status Email",
                        body: "Build was successful."
                    )
                }
                failure {
                    emailext (
                        to: "lguilding@deakin.edu.au",
                        subject: "Build Failure Notification",
                        body: "Build failed. Please check the logs for details."
                    )
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
