pipeline {
    agent any
    stages {
        stage('Build & Test') {
            steps {
                // Use 'bat' for Windows
                bat 'mvn clean test'
            }
        }
        stage('Security Scan') {
            // Requirement: Different strategy for Release branches
            when { branch 'release/*' }
            steps {
                echo 'Performing Security Scan on Release Branch...'
            }
        }
        stage('Deploy') {
            // Requirement: Full CI/CD only for Main
            when { branch 'main' }
            steps {
                echo 'Deploying from Main branch...'
            }
        }
    }
}