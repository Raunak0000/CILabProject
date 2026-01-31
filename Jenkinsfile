pipeline {
    agent any
    stages {
        stage('Build & Test') {
            steps {
                echo 'Building and testing on all branches...'
                bat 'mvn clean test' // Uses the Maven you configured in Task 2
            }
        }
        stage('Security Scan') {
            when { branch 'release/*' } // Requirement: Only runs on release branches
            steps {
                echo 'Performing Security Scan for Release...'
            }
        }
        stage('Deployment') {
            when { branch 'main' } // Requirement: Full CI/CD for main branch
            steps {
                echo 'Deploying to Production environment...'
            }
        }
    }
}