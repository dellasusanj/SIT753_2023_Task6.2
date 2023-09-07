pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Using build automation tool: Maven"
            }
        }
        
        stage('Unit and Integration Tests') {
            steps {
                echo "Using Unit and Integration Test automation tool: JUnit"
            }
            post {
                success{
                    mail to: "sleo93880@gmail.com",
                    subject: "Test Status - Success",
                    body: "Unit and Integration Tests were successful",
                    attachLog: true
                }
                failure{
                    mail to: "sleo93880@gmail.com",
                    subject: "Test Status - Failure",
                    body: "Unit and Integration Tests were failed",
                    attachLog: true
                }
            }
        }
        
        stage('Code Analysis') {
            steps {
                echo "Using Code Analysis tool: SonarQube"
            }
        }
        stage('Security Scan') {
            steps {
                echo "Using Security Scanning tool: OWASP ZAP"
            }
            post {
                success{
                    mail to: "sleo93880@gmail.com",
                    subject: "Security Scan Status - Success",
                    body: "Security scan was successful",
                    attachLog: true
                }
                failure{
                    mail to: "sleo93880@gmail.com",
                    subject: "Security Scan Status - Failure",
                    body: "Security scan was failed",
                    attachLog: true
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo "Tool used for Deploying to Staging: Docker"
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo "Tool used for Integration Tests on Staging: Selenium"
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Tool used for Deploying to Production: Kubernetes"
            }
        }
    }
    post {
        success {
            // Send notification email for successful stages
            emailext(
                subject: "Pipeline Status - Success",
                body: "The pipeline ran successfully.",
                to: "sleo93880@gmail.com",
                attachLog: true
            )
        }
        failure {
            // Send notification email for failed stages
            emailext(
                subject: "Pipeline Status - Failure",
                body: "The pipeline has failed.",
                to: "sleo93880@gmail.com",
                attachLog: true
            )
        }
    }
}
