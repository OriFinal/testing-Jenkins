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
                    mail to: "final.divergence.drive@gmail.com",
                    subject: "Build Status Email",
                    body: "Build was successful!"
            )
        }
        
        failure {
                    mail to: "final.divergence.drive@gmail.com",
                    subject: "Build Status Email",
                    body: "Build was failure!"
            )
        }
    }
}
