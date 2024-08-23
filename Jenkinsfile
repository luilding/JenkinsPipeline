pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Building"
            }
            post{
                success{
                    mail to: "lguilding@deakin.edu.au",
                    subject: "Build status email",
                    body: "build was successful"
                }
            }
        }
        stage("Test"){
            steps{
                echo "Testing ..."
            }
        }
        stage("Deploy"){
            steps{
                echo "Deploying ..."
            }
        }
    }
}

