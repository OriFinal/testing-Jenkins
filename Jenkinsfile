pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
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
         stage('Complee') {
            steps {

                echo "Completed !"
            }
        }
    }
    
    post {
        success {
            // Send an email notification on successful build
            emailext (
                subject: "Pipeline Successful: ${currentBuild.fullDisplayName}",
                body: "The Jenkins pipeline for your project has been successfully executed.",
                to: 's223623238@deakin.edu.au', // Replace with your email address
                attachLog: true
            )
        }
        
        failure {
            // Send an email notification on build failure
            emailext (
                subject: "Pipeline Failed: ${currentBuild.fullDisplayName}",
                body: "The Jenkins pipeline for your project has failed. Please investigate and take necessary actions.",
                to: 's223623238@deakin.edu.au', // Replace with your email address
                attachLog: true
            )
        }
    }
}
