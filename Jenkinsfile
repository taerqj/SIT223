pipeline{
    agent any
    
    stages{
        stage("Build"){
            steps{
                echo "Building project using Gradle"
            }
        }
        stage("Unit and Integration Tests"){
            steps{
                echo "Running Unit Tests using JUnit"
                echo "Running Integration Tests using Postman"
            }
            post{
                success{
                    mail to: "jabirtaerq@gmail.com",
                        subject: "Unit and Integration Tests",
                        body: "Successful Tests."
                }
                failure{
                    mail to: "jabirtaerq@gmail.com",
                        subject: "Unit and Integration Tests",
                        body: "Failed Tests."
                }
            }
        }
        stage("Code Analysis")
        {
            steps{
                echo "Running Code Analysis using SonarScanner"
            }
        }
        stage("Security Scan"){
            steps{
                echo "Running Security Scans using OWASP ZAP"
            }
            post{
                success{
                    mail to: "jabirtaerq@gmail.com",
                        subject: "Security Scan",
                        body: "Successful Scan."
                }
                failure{
                    mail to: "jabirtaerq@gmail.com",
                        subject: "Security Scan",
                        body: "Failed Scan."
                }
            }
        }
        stage("Deploy to Staging"){
            steps{
                echo "Deploying using AWS EC2 Instance"
            }
        }
        stage("Integration Tests on Staging"){
            steps{
                echo "Running Integration Tests on Staging"
            }
        }
        stage("Deploy to Production"){
            steps{
                echo "Deploying application using AWS EC2 Instance"
            }
        }
        
    }
}