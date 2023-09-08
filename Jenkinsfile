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
                    echo "Successful Unit and Integration Tests"
                    mail to: "s222011266@deakin.edu.au",
                        subject: "Unit and Integration Tests"
                        body: "Successful Tests."
                }
                failure{
                    echo "Failure in Unit and Integration Tests"
                    mail to: "s222011266@deakin.edu.au",
                        subject: "Unit and Integration Tests"
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
                    echo "Successful Security Scan"
                    mail to: "s222011266@deakin.edu.au",
                        subject: "Security Scan"
                        body: "Successful Scan."
                }
                failure{
                    echo "Failure in Security Scan"
                    mail to: "s222011266@deakin.edu.au",
                        subject: "Security Scan"
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