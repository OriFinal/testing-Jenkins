pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Use Maven to build your code
                sh 'mvn clean package'
            }
            // Justification: Maven is a popular build automation tool for Java projects, ensuring the code compiles and packages correctly.
        }

        stage('Unit and Integration Tests') {
            steps {
                // Use JUnit for running unit tests
                sh 'mvn test'
                // Use Selenium for web application UI testing
                sh 'selenium-tests.sh'
            }
            // Justification: JUnit is a widely-used unit testing framework for Java, while Selenium is used for automated web application testing.
        }

        stage('Code Analysis') {
            steps {
                // Integrate SonarQube for code analysis
                sh 'sonar-scanner'
            }
            // Justification: SonarQube analyzes code for quality, identifies issues, and enforces coding standards.
        }

        stage('Security Scan') {
            steps {
                // Use OWASP ZAP for security scanning
                sh 'owasp-zap-scan.sh'
            }
            // Justification: OWASP ZAP identifies security vulnerabilities in your application code.
        }

        stage('Deploy to Staging') {
            steps {
                // Use AWS CLI for deploying to AWS ECS (Elastic Container Service)
                sh 'aws ecs deploy-to-staging.sh'
            }
            // Justification: AWS CLI automates the deployment process to a staging environment, making it repeatable and efficient.
        }

        stage('Integration Tests on Staging') {
            steps {
                // Run integration tests on the staging environment using a testing framework like TestNG
                sh 'testng-staging-tests.sh'
            }
            // Justification: Integration tests on staging ensure the application functions as expected in a production-like environment.
        }

        stage('Deploy to Production') {
            steps {
                // Use AWS CLI to deploy to a production AWS EC2 instance
                sh 'aws ec2 deploy-to-production.sh'
            }
            // Justification: AWS CLI is used to deploy the application to a production server, making it accessible to users.
        }
    }
}
