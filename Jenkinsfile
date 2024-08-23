pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Building underway using Maven"
            }
        }
        stage("Unit and Integration Tests"){
            steps{
                echo "Running Unit and integration testing tools: pytest and unittest"
            }
            post{
                failure {
                    emailext attachLog: true,
                    to: "lguilding@deakin.edu.au",
                    subject: "Unit and integration test failure status email",
                    body: "unit and integration tests failed"
                    
                }
                success{
                    emailext attachLog: true,
                    to: "lguilding@deakin.edu.au",
                    subject: "Unit and integration test success status email",
                    body: "unit and integration tests were successful"
                }
            }            
        }
        stage("Code Analysis"){
            steps{
                echo "Running code analysis tool: pyint."
            }
        }
        stage("Security Scan"){
            steps{
                echo "Running security scanning tool: PyT"
            }
            post{
                failure {
                    emailext attachLog: true,
                    to: "lguilding@deakin.edu.au",
                    subject: "Security scan failure status email",
                    body: "Security scan failed"
                    
                }
                success{
                    emailext attachLog: true,
                    to: "lguilding@deakin.edu.au",
                    subject: "Security scan success status email",
                    body: "Security scan success"
                }
            } 
        }
        stage("Deploy to Staging"){
            steps{
                echo "Deploying to AWS staging environment"
            }
        }
        stage("Integration Tests on Staging"){
            steps{
                echo "Running intergration tests in staging with selenium "
            }
            post{
                failure {
                    emailext attachLog: true,
                    to: "lguilding@deakin.edu.au",
                    subject: "Staging integration test failure status email",
                    body: "integration test failed in staging"
                    
                }
                success{
                    emailext attachLog: true,
                    to: "lguilding@deakin.edu.au",
                    subject: "Staging integration test success status email",
                    body: "integration test in success in staging"
                }
            } 
        }
        stage("Deploy to Production"){
            steps{
                echo "Deployed to AWS production environment"
            }        
        }
    }
}
