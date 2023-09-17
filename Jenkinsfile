pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {

                echo "Using Maven tool"
            }
        }
        
        stage('Unit and Integration Tests') {
            steps {
                
                echo "Using JUnit or Selenium"
            }
        }
        
        stage('Code Analysis') {
            steps {

                echo "Using SonarQube"
            }
        }
         stage('Security Scan') {
            steps {

                echo "Using OWASP ZAP!"
            }
        }
        stage('Deploy to Staging') {
            steps {

                echo "Deploying to AWS EC2"
            }
        }
        stage('Integration Tests on Staging') {
            steps {

                echo "Testing with TestNG"
            }
        }
        stage('Deploy to Production') {
            steps {

                echo "Deploying to AWS EC2+"
            }
        }
    }
    
    post {
        success {
            // Send an email notification on successful build
            emailext (
                subject: "Pipeline Successful: ${currentBuild.fullDisplayName}",
                body: "The Jenkins pipeline for your project has been successfully executed.",
                mail to: 'final.divergence.drive@gmail.com', // Replace with your email address
                attachLog: true
            )
        }
        
        failure {
            // Send an email notification on build failure
            emailext (
                subject: "Pipeline Failed: ${currentBuild.fullDisplayName}",
                body: "The Jenkins pipeline for your project has failed. Please investigate and take necessary actions.",
                mail to: 'final.divergence.drive@gmail.com', // Replace with your email address
                attachLog: true
            )
        }
    }
}
